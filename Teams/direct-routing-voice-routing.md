---
title: Configurare il routing delle chiamate per il routing diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare il routing delle chiamate con Microsoft Direct Routing.
ms.openlocfilehash: a7f80a71aa83e255efe81b82ce57026ed0749165
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046666"
---
# <a name="configure-call-routing-for-direct-routing"></a>Configurare il routing delle chiamate per il routing diretto

Questo articolo descrive come configurare il routing delle chiamate per il routing diretto. Questo è il passaggio 3 della procedura seguente per configurare il routing diretto:

- Passaggio 1. [Connettere SBC con Sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per routing diretto, voce e segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3. Configurare il routing delle chiamate** (questo articolo)
- Passaggio 4. [Tradurre numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto](direct-routing-configure.md).

## <a name="call-routing-overview"></a>Panoramica del routing delle chiamate

Sistema telefonico Microsoft dispone di un meccanismo di routing che consente di inviare una chiamata a uno specifico session border controller (SBC) basato su: 

- Il modello di numero denominato 
- Il modello di numero chiamato più l'utente specifico che effettua la chiamata
 
Gli SBC possono essere designati come attivi e di backup. Quando la scheda SBC configurata come attiva non è disponibile per un percorso di chiamata specifico, la chiamata verrà instradata a una scheda SBC di backup.
 
Il routing delle chiamate è costituito dai seguenti elementi: 

- **Criteri di routing delle chiamate** : definito anche criterio di routing vocale. Contenitore per gli utilizzi PSTN, che può essere assegnato a un utente o a più utenti. 

- **Utilizzi PSTN** : contenitore per route vocali e utilizzi PSTN, che possono essere condivisi in criteri di routing vocale diversi. 

- **Route vocali** : modello numerico e set di gateway PSTN online da usare per le chiamate in cui il numero di chiamata corrisponde allo schema.

- **Gateway PSTN online** : puntatore a un'interfaccia SBC che archivia anche la configurazione applicata quando una chiamata viene eseguita tramite SBC, ad esempio il P-Asserted-Identity (PAI) o i codec preferiti. possono essere aggiunti ai percorsi vocali.

## <a name="voice-routing-policy-considerations"></a>Considerazioni sui criteri di routing vocale

Se un utente dispone di una licenza per un piano per chiamate, le chiamate in uscita di quell'utente vengono automaticamente instradate tramite l'infrastruttura PSTN del piano per chiamate Microsoft. Se configuri e assegni un criterio di routing vocale online a un utente del Piano per chiamate, le chiamate in uscita di quell'utente vengono controllate per determinare se il numero comporre corrisponde a uno schema numerico definito nel criterio di routing vocale online. Se esiste una corrispondenza, la chiamata viene instradata attraverso il trunk Routing diretto. Se non c'è corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano per chiamate.

> [!CAUTION]
> Se si configura e si applica il criterio di routing vocale online (predefinito a livello di organizzazione), tutti gli utenti con riconoscimento vocale dell'organizzazione erediteranno tale criterio, il che potrebbe comportare l'instradamento accidentale di chiamate PSTN da parte degli utenti del piano per chiamate e di Operator Connect a un trunk routing diretto. Se non si vuole che tutti gli utenti usno il criterio di routing vocale online globale, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per i comandi vocali.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Esempio 1: Routing vocale con un utilizzo PSTN

Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso delle chiamate.

**Flusso di chiamata 1 (a sinistra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non sono disponibili sbc1.contoso.biz né sbc2.contoso.biz, la chiamata viene interrotta. 

**Flusso delle chiamate 2 (a destra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene prima instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non è disponibile alcuna scheda SBC, verrà tentato il percorso con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz). Se nessuno degli SBC è disponibile, la chiamata viene interrotta. 

![Mostra esempi di criteri di routing vocale.](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In entrambi gli esempi, mentre al percorso vocale sono assegnate priorità, le schede SBC nei percorsi vengono provate in ordine casuale.

  > [!NOTE]
  > A meno che l'utente non disponga anche di una licenza per il piano di chiamate Microsoft, le chiamate a qualsiasi numero tranne i numeri che corrispondono ai modelli +1 425 XXX XX XX o +1 206 XXX XX XX nella configurazione dell'esempio vengono eliminati. Se l'utente dispone di una licenza per il Piano per chiamate, la chiamata viene automaticamente instradata in base ai criteri del Piano per chiamate Microsoft. Il piano per chiamate Microsoft si applica automaticamente come ultimo itinerario a tutti gli utenti con licenza Piano per chiamate Microsoft e non richiede una configurazione aggiuntiva del routing delle chiamate.

Nell'esempio illustrato nel diagramma seguente viene aggiunto un percorso vocale per l'invio di chiamate a tutti gli altri numeri degli Stati Uniti e del Canada (chiamate indirizzate a modello di numero +1 XXX XXX XX XX).

![Mostra i criteri di routing vocale con una terza route.](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Sistema telefonico Microsoft e Piano per chiamate Microsoft), viene usato il percorso automatico. Se nulla corrisponde ai modelli numerici nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano per chiamate Microsoft. Se l'utente ha solo Microsoft Phone System, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.

  > [!NOTE]
  > Il valore Priority per il percorso "Other +1" non ha importanza in questo caso perché esiste un solo percorso che corrisponde allo schema +1 XXX XXX XX XX. Se un utente effettua una chiamata a +1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz non sono disponibili, la chiamata viene interrotta.

La tabella seguente riepiloga la configurazione utilizzando tre route vocali. In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo di PSTN, "Stati Uniti e Canada".  Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo di PSTN è associato ai criteri di routing vocale "Solo Stati Uniti".

|**Utilizzo PSTN**|**Percorso vocale**|**Schema numerico**|**Priority**|**Sbc**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+1(425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Percorso attivo per i numeri chiamati +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+1(425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri chiamati +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Esempio 1: Passaggi di configurazione

L'esempio seguente illustra come:

1. Creare un singolo utilizzo PSTN.
2. Configurare tre percorsi vocali.
3. Creare un criterio di routing vocale.
4. Assegnare il criterio a un utente denominato Spencer Low.

È possibile usare [l'interfaccia di amministrazione di Microsoft Teams](#admincenterexample1) o [PowerShell](#powershellexample1) per eseguire questa procedura.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: Creare l'utilizzo pstn "Stati Uniti e Canada"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Routing diretto** **vocale** >  e quindi nell'angolo in alto a destra selezionare **Gestisci record di utilizzo PSTN**.
2. Fare clic su **Aggiungi**, digitare **Stati Uniti e Canada** e quindi fare clic su **Applica**.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: Creare tre itinerari vocali (Redmond 1, Redmond 2 e Altro +1)

I passaggi seguenti descrivono come creare un percorso vocale. Usare questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e Other +1 per questo esempio usando le impostazioni descritte nella tabella precedente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Routing diretto** **vocale** >  e quindi seleziona la scheda **Route vocali**.
2. Fare clic su **Aggiungi** e quindi immettere un nome e una descrizione per il percorso vocale.
3. Impostare la priorità e specificare il modello di numero comporre.
4. Per registrare una scheda SBC con il percorso vocale, in **SBC registrati (facoltativo)** fare clic su **Aggiungi SBC**, selezionare gli SBC da registrare e quindi fare clic su **Applica**.
5. Per aggiungere record di utilizzo PSTN, in **Record di utilizzo PSTN (facoltativo)** fare clic su **Aggiungi utilizzo PSTN**, selezionare i record PSTN da aggiungere e quindi fare clic su **Applica**.
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Criteri di routing vocale** >  e quindi fare clic su **Aggiungi**.
2. Digitare **Solo STATI UNITI** come nome e aggiungere una descrizione.
3. In **Record di utilizzo PSTN** fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **Applica**.
4. Fare clic su **Salva**.

Per altre informazioni, vedere [Gestire i criteri di routing vocale](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: Assegnare il criterio di routing vocale a un utente denominato Spencer Low

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **Criteri** e quindi accanto a **Criteri assegnati** fare clic su **Modifica**.
3. In **Criteri di routing vocale** seleziona il criterio "Solo Stati Uniti", quindi fai clic su **Salva**.

Per altre informazioni, vedere [Gestire i criteri di routing vocale](manage-voice-routing-policies.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: Creare l'utilizzo pstn "Stati Uniti e Canada"

In una sessione remota di PowerShell in Skype for Business Online digitare:

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

L'esempio seguente mostra il risultato dell'esecuzione del `(Get-CSOnlinePSTNUsage).usage` comando di PowerShell per visualizzare i nomi completi (non troncati):

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: Creare tre itinerari vocali (Redmond 1, Redmond 2 e Altro +1)

Per creare il percorso "Redmond 1", in una sessione di PowerShell in Skype for Business Online, immettere:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Che restituisce:

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

Per creare il percorso Redmond 2, immettere:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Per creare la route Altro +1, immettere:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Assicurarsi che l'espressione regolare nell'attributo NumberPattern sia un'espressione valida. È possibile testarlo usando questo sito Web: [https://www.regexpal.com](https://www.regexpal.com)

In alcuni casi, è necessario instradare tutte le chiamate allo stesso SBC; use -NumberPattern ".*"

Instradare tutte le chiamate allo stesso SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Verificare di aver configurato correttamente il percorso eseguendo il `Get-CSOnlineVoiceRoute` comando di PowerShell usando le opzioni come illustrato di seguito:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Che dovrebbe restituire:

```console
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
```

Nell'esempio, alla route "Altro +1" è stata assegnata automaticamente la priorità 4. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio

In una sessione di PowerShell in Skype for Business Online digitare:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Il risultato è illustrato in questo esempio:

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: Assegnare il criterio di routing vocale a un utente denominato Spencer Low

In una sessione di PowerShell in Skype for Business Online digitare:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Convalidare l'assegnazione dei criteri immettendo questo comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Il comando restituisce quanto segue:

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Esempio 2: Routing vocale con più utilizzi PSTN

I criteri di routing vocale creati nell'esempio 1 consentono solo le chiamate ai numeri di telefono negli Stati Uniti e in Canada, a meno che all'utente non sia assegnata anche la licenza del piano per chiamate Microsoft.

Nell'esempio seguente è possibile creare il criterio di routing vocale "Nessuna restrizione". I criteri riutilizzano l'utilizzo di PSTN "Stati Uniti e Canada" creato nell'esempio 1, nonché il nuovo utilizzo PSTN "internazionale". Questa politica indirizza tutte le altre chiamate alle sbc2.contoso.biz e sbc5.contoso.biz.

Gli esempi mostrati assegnano il criterio Solo Stati Uniti all'utente Spencer Low e il criterio Nessuna restrizione all'utente John Woods in modo che il routing avvenga nel modo seguente:

- Spencer Low – Politica solo usa.  Le chiamate sono consentite solo ai numeri degli Stati Uniti e del Canada. Quando si chiama l'intervallo di numeri redmond, è necessario utilizzare il set specifico di SBC. I numeri non statunitensi verranno instradati solo se all'utente è assegnata la licenza per il Piano per chiamate.

- John Woods – Politica internazionale.  Le chiamate sono consentite a qualsiasi numero. Quando si chiama l'intervallo di numeri redmond, è necessario utilizzare il set specifico di SBC. I numeri non statunitensi verranno instradati utilizzando sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra i criteri di routing vocale assegnati all'utente Spencer Low.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Sistema telefonico Microsoft e Piano per chiamate Microsoft), viene usato il percorso automatico. Se nulla corrisponde ai modelli numerici nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano per chiamate Microsoft.  Se l'utente ha solo Microsoft Phone System, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.

![Mostra i criteri di routing vocale assegnati all'utente John Woods.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

La tabella seguente riepiloga le designazioni di utilizzo e le route vocali dei criteri di routing "Nessuna restrizione". 

| Utilizzo PSTN | Percorso vocale | Schema numerico | Priority | Sbc | Descrizione |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+1(425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Percorso attivo per i numeri del destinatario chiamata +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+1(425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri del destinatario chiamata +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)|
|Internazionale|Internazionale|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Itinerario per qualsiasi modello di numero |

  > [!NOTE]
  > - L'ordine degli utilizzi PSTN nei criteri di routing vocale è fondamentale. Gli utilizzi vengono applicati in ordine e, se viene trovata una corrispondenza nel primo utilizzo, gli altri utilizzi non vengono mai valutati. L'utilizzo PSTN "internazionale" deve essere effettuato dopo l'utilizzo di PSTN "Stati Uniti e Canada". Per modificare l'ordine degli utilizzi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Ad esempio, per modificare l'ordine da "Stati Uniti e Canada" primo e "Internazionale" secondo all'esecuzione dell'ordine inverso:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La priorità per le route vocali "Altro +1" e "Internazionale" viene assegnata automaticamente. Non importa se hanno priorità più basse di "Redmond 1" e "Redmond 2".

## <a name="example-2-configuration-steps"></a>Esempio 2: Passaggi di configurazione

L'esempio seguente illustra come:

1. Creare un nuovo utilizzo PSTN denominato Internazionale.
2. Creare un nuovo percorso vocale denominato Internazionale.
3. Creare un criterio di routing vocale denominato Nessuna restrizione.
4. Assegnare il criterio all'utente John Woods.

È possibile usare [l'interfaccia di amministrazione di Microsoft Teams](#admincenterexample2) o [PowerShell](#powershellexample2) per eseguire questa procedura.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: Creare l'utilizzo PSTN "internazionale"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Routing diretto** **vocale** >  e quindi nell'angolo in alto a destra selezionare **Gestisci record di utilizzo PSTN**.
2. Fare clic su **Aggiungi**, digitare **Internazionale** e quindi fare clic su **Applica**.

#### <a name="step-2-create-the-international-voice-route"></a>Passaggio 2: Creare il percorso vocale "Internazionale"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Routing diretto** **vocale** >  e quindi seleziona la scheda **Route vocali**.
2. Fare clic su **Aggiungi**, immettere "Internazionale" come nome e quindi aggiungere la descrizione.
3. Impostare la priorità su 4 e quindi impostare il modello di numero comporre su \d+.
4. In **Schede SBCs registrate (facoltativo)** fare clic su **Aggiungi schede SBC**, selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **Applica**.
5. In **Record di utilizzo PSTN (facoltativo)** fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Internazionale" e quindi fare clic su **Applica**.
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione" e aggiungere al criterio gli utilizzi PSTN "Stati Uniti e Canada" e "Internazionale"

L'utilizzo di PSTN "Stati Uniti e Canada" viene riutilizzato in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Criteri di routing vocale** >  e quindi fare clic su **Aggiungi**.
2. Digitare **Nessuna restrizione** come nome e aggiungere una descrizione.
3. In **Record di utilizzo PSTN** fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "Internazionale". Fare clic su **Applica**.

    Prendere nota dell'ordine di utilizzo di PSTN:

    - Se viene effettuata una chiamata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come in questo esempio, la chiamata segue il percorso impostato nell'utilizzo "Stati Uniti e Canada" e viene applicata la logica di routing speciale. Ovvero, la chiamata viene prima instradata usando sbc1.contoso.biz e sbc2.contoso.biz, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.

    - Se l'utilizzo pstn "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.

4. Fare clic su **Salva**.

Per altre informazioni, vedere [Gestire i criteri di routing vocale](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Passaggio 4: Assegnare il criterio di routing vocale a un utente denominato John Woods

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **Criteri** e quindi accanto a **Criteri assegnati** fare clic su **Modifica**.
3. In **Criteri di routing vocale** seleziona il criterio "Nessuna restrizione", quindi fai clic su **Salva**.

Il risultato è che il criterio vocale applicato alle chiamate di John Woods è illimitato e seguirà la logica del routing delle chiamate disponibile per le chiamate internazionali, statunitensi e canadesi.

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: Creare l'utilizzo PSTN "internazionale"

In una sessione remota di PowerShell in Skype for Business Online immettere:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Passaggio 2: Creare un nuovo percorso vocale denominato "Internazionale"

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

Che restituisce:

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione"

L'utilizzo di PSTN "Redmond 1" e "Redmond" viene riutilizzato in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Prendere nota dell'ordine di utilizzo di PSTN:

  - Se una chiamata effettuata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come nell'esempio seguente, la chiamata segue il percorso impostato nell'utilizzo "Stati Uniti e Canada" e viene applicata la logica di routing speciale. Ovvero, la chiamata viene prima instradata usando sbc1.contoso.biz e sbc2.contoso.biz, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.

  - Se l'utilizzo pstn "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing. Immettere il comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Che restituisce:

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Passaggio 4: Assegnare il criterio di routing vocale all'utente denominato John Woods

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Verifica quindi l'attività usando il comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Che restituisce:

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

Il risultato è che il criterio vocale applicato alle chiamate di John Woods è senza restrizioni e seguirà la logica del routing delle chiamate disponibile per le chiamate internazionali, statunitensi e canadesi.

## <a name="run-a-self-diagnostics-tool"></a>Eseguire uno strumento di auto-diagnostica

Gli utenti amministratori di Microsoft 365 hanno accesso alla diagnostica che può essere eseguita all'interno del tenant per verificare che un utente sia configurato correttamente per il routing diretto. 

> [!NOTE]
>Questa funzionalità non è disponibile per Microsoft 365 Government, Microsoft 365 gestito da 21Vianet o Microsoft 365 Germany.

Selezionare Esegui test, come indicato di seguito. La diagnostica verrà popolata nel Centro Amministrazione Microsoft 365.
>> [!div class="nextstepaction"]
>> [Eseguire test: Routing diretto di Teams](https://aka.ms/TeamsDirectRoutingDiag)

La diagnostica esegue un'ampia gamma di verifiche.

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
