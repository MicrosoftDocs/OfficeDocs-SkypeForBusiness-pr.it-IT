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
description: Informazioni su come configurare il routing vocale con Telefono Microsoft routing diretto di sistema.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383980"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Configurare il routing vocale per il routing diretto

Questo articolo descrive come configurare il routing vocale per Sistema telefonico routing diretto.  Questo è il passaggio 3 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Connessione SBC con Telefono Microsoft sistema e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3. Configurare il routing vocale** (questo articolo)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)

## <a name="voice-routing-overview"></a>Panoramica del routing vocale

Telefono Microsoft Il sistema ha un meccanismo di routing che consente di inviare una chiamata a uno specifico Session Border Controller (SBC) in base a: 

- Il modello di numero chiamato 
- Il modello di numero chiamato più l'utente specifico che effettua la chiamata
 
Gli SBC possono essere designati come attivi e di backup. Quando la SBC configurata come attiva non è disponibile per un percorso di chiamata specifico, la chiamata verrà instradata a un SBC di backup.
 
Il routing vocale è costituito da elementi seguenti: 

- **Criteri di routing vocale:** contenitore per gli utilizzi PSTN, che può essere assegnato a un utente o a più utenti. 

- **Utilizzi PSTN:** contenitore per route vocali e utilizzi PSTN, che può essere condiviso in criteri di routing vocale diversi. 

- **Route vocali:** uno schema di numeri e un set di gateway PSTN online da usare per le chiamate in cui il numero di chiamata corrisponde al modello.

- **Gateway PSTN online:** puntatore a un SBC in cui viene archiviata anche la configurazione applicata quando una chiamata viene inoltrata tramite SBC, ad esempio l'inoltro P-Asserted-Identity (PAI) o i codec preferiti. può essere aggiunto alle route vocali.

## <a name="voice-routing-policy-considerations"></a>Considerazioni sui criteri di routing vocale

Se un utente ha una licenza per il piano di chiamata, le chiamate in uscita dell'utente vengono automaticamente instradati tramite l'infrastruttura PSTN del piano chiamate Microsoft. Se si configurano e si assegnano criteri di routing vocale online a un utente del piano di chiamata, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composto corrisponde a uno schema di numeri definito nel criterio di routing vocale online. Se c'è una corrispondenza, la chiamata viene instradata attraverso il trunk direct routing. Se non c'è corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano per chiamate.

> [!CAUTION]
> Se si configura e si applica il criterio di routing vocale online globale (predefinito a livello di organizzazione), tutti gli utenti abilitati per la voce dell'organizzazione erediteranno tale criterio, il che potrebbe comportare l'instradamento involontario delle chiamate PSTN degli utenti del piano di chiamata a un trunk di routing diretto. Se non si vuole che tutti gli utenti usino il criterio di routing vocale online globale, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per la voce.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Esempio 1: Routing vocale con un solo utilizzo PSTN

Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso di chiamate.

**Chiama Flow 1 (a sinistra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non sbc1.contoso.biz né sbc2.contoso.biz disponibili, la chiamata viene interrotta. 

**Chiama Flow 2 (a destra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene prima instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se nessuno dei due SBC è disponibile, verrà provato il percorso con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz). Se nessuno dei SBC è disponibile, la chiamata viene interrotta. 

![Esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In entrambi gli esempi, mentre alla route vocale sono assegnate priorità, i SBC nelle route vengono provati in ordine casuale.

  > [!NOTE]
  > A meno che l'utente non abbia anche una licenza per il piano per chiamate Microsoft, le chiamate a qualsiasi numero tranne i numeri che corrispondono ai modelli +1 425 XXX XX XX o +1 206 XXX XX XX nella configurazione di esempio vengono eliminate. Se l'utente ha una licenza per il piano di chiamata, la chiamata viene instradata automaticamente in base ai criteri del Piano chiamate Microsoft. Il Piano chiamate Microsoft si applica automaticamente come ultimo percorso a tutti gli utenti con la licenza Microsoft Calling Plan e non richiede una configurazione aggiuntiva del routing delle chiamate.

Nell'esempio illustrato nel diagramma seguente viene aggiunta una route vocale per inviare chiamate a tutti gli altri numeri statunitensi e canadesi (chiamate che vengono chiamate con schema di numeri +1 XXX XX XX).

![Mostra i criteri di routing vocale con una terza route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Telefono Microsoft Sistema e Piano chiamate Microsoft), viene usato il percorso automatico. Se nulla corrisponde ai modelli di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il Piano chiamate Microsoft. Se l'utente ha solo Telefono Microsoft sistema, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.

  > [!NOTE]
  > Il valore Priority per la route "Other +1" non è importante in questo caso perché esiste una sola route che corrisponde al modello +1 XXX XX XX. Se un utente effettua una chiamata a +1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene interrotta.

La tabella seguente riepiloga la configurazione usando tre route vocali. In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo PSTN, "Stati Uniti e Canada".  Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo PSTN è associato al criterio di routing vocale "Solo stati Uniti".

|**Utilizzo PSTN**|**Route vocale**|**Schema numerico**|**Priority**|**SBC**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Percorso attivo per i numeri chiamati +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri denominati +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Percorso per i numeri chiamati +1 XXX XXX XX XX (tranne +1 425 XXX XX XX o +1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Esempio 1: Passaggi di configurazione

L'esempio seguente mostra come:

1. Creare un singolo utilizzo PSTN.
2. Configurare tre route vocali.
3. Creare un criterio di routing vocale.
4. Assegnare il criterio a un utente denominato Spencer Low.

È possibile usare [l'Microsoft Teams di amministrazione o](#admincenterexample1) [PowerShell](#powershellexample1) per eseguire questa procedura.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: Creare l'utilizzo PSTN "Stati Uniti e Canada"

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing e quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**
2. Fare **clic su** Aggiungi , digitare Stati Uniti e **Canada** e quindi fare clic su **Applica**.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: Creare tre route vocali (Redmond 1, Redmond 2 e Other +1)

La procedura seguente descrive come creare una route vocale. Usare questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e Other +1 per questo esempio usando le impostazioni descritte nella tabella precedente.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Routing** vocale diretto e quindi  >  selezionare la **scheda Route** vocali.
2. Fare **clic su** Aggiungi e quindi immettere un nome e una descrizione per la route vocale.
3. Impostare la priorità e specificare il modello di numero composto.
4. Per registrare un SBC con la route vocale, in SBC registrati **(facoltativo)** fare clic su Aggiungi **SBC,** selezionare gli SBC da registrare e quindi fare clic su **Applica.**
5. Per aggiungere record di utilizzo PSTN, in Record di utilizzo **PSTN (facoltativo)** fare clic su Aggiungi utilizzo **PSTN,** selezionare i record PSTN da aggiungere e quindi fare clic su **Applica.**
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare **a** Criteri di  >  **routing vocale** e quindi fare clic su **Aggiungi.**
2. Digitare **Solo stati Uniti** come nome e aggiungere una descrizione.
3. In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **Applica.**
4. Fare clic su **Salva**.

Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: Assegnare i criteri di routing vocale a un utente denominato Spencer Low

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare **clic su** Criteri e quindi accanto a Criteri **assegnati** fare clic su **Modifica.**
3. In **Criteri routing vocale** selezionare il criterio "Solo stati Uniti" e quindi fare clic su **Salva.**

Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: Creare l'utilizzo PSTN "Stati Uniti e Canada"

In una sessione remota di PowerShell in Skype for Business Online digitare:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Verificare che l'utilizzo sia stato creato immettendo:

```PowerShell
Get-CSOnlinePSTNUsage
``` 

Che restituisce un elenco di nomi che potrebbero essere troncati:

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

L'esempio seguente mostra il risultato dell'esecuzione del comando `(Get-CSOnlinePSTNUsage).usage` PowerShell per visualizzare i nomi completi (non troncati):

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: Creare tre route vocali (Redmond 1, Redmond 2 e Other +1)

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

Per creare il percorso di Redmond 2, immettere:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Per creare il percorso Altro +1, immettere:

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

Verificare di aver configurato correttamente la route eseguendo il comando `Get-CSOnlineVoiceRoute` di PowerShell usando le opzioni come illustrato:

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

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: Assegnare i criteri di routing vocale a un utente denominato Spencer Low

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

Il criterio di routing vocale creato nell'esempio 1 consente solo le chiamate a numeri di telefono negli Stati Uniti e in Canada, a meno che all'utente non sia assegnata anche la licenza Del piano per chiamate Microsoft.

Nell'esempio seguente è possibile creare il criterio di routing vocale "Nessuna restrizione". Il criterio riutilizza l'utilizzo PSTN "Stati Uniti e Canada" creato nell'esempio 1, oltre al nuovo utilizzo PSTN "internazionale". Questo criterio indirizza tutte le altre chiamate agli SBC sbc2.contoso.biz e sbc5.contoso.biz.

Gli esempi illustrati assegnano il criterio Solo stati Uniti all'utente Spencer Low e il criterio Nessuna restrizione all'utente John Woods in modo che il routing si verifichi come segue:

- Politica di Spencer Low - Solo stati Uniti.  Le chiamate sono consentite solo a numeri statunitensi e canadesi. Quando si chiama l'intervallo di numeri di Redmond, è necessario usare il set specifico di SBC. I numeri non statunitensi non verranno instradati a meno che all'utente non sia assegnata la licenza per il piano di chiamata.

- John Woods - Politica internazionale.  Le chiamate sono consentite a qualsiasi numero. Quando si chiama l'intervallo di numeri di Redmond, è necessario usare il set specifico di SBC. I numeri non statunitensi verranno instradati usando sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra i criteri di routing vocale assegnati all'utente Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Telefono Microsoft Sistema e Piano chiamate Microsoft), viene usato il percorso automatico. Se nulla corrisponde ai modelli di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata usando il Piano chiamate Microsoft.  Se l'utente ha Telefono Microsoft sistema, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.

![Mostra i criteri di routing vocale assegnati all'utente John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

La tabella seguente riepiloga le designazioni di utilizzo e le route vocali dei criteri di routing "Nessuna restrizione". 

| Utilizzo PSTN | Route vocale | Schema numerico | Priority | SBC | Descrizione |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Percorso attivo per i numeri dei callee +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri dei callee +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Percorso per i numeri dei callee +1 XXX XXX XX XX (ad eccezione di +1 425 XXX XX XX o +1 206 XXX XX XX)|
|Internazionale|Internazionale|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Percorso per qualsiasi schema di numeri |

  > [!NOTE]
  > - L'ordine di utilizzo di PSTN nei criteri di routing vocale è fondamentale. Gli utilizzi vengono applicati nell'ordine e, se viene trovata una corrispondenza nel primo utilizzo, gli altri utilizzi non vengono mai valutati. L'utilizzo PSTN "internazionale" deve essere inserito dopo l'utilizzo PSTN "Stati Uniti e Canada". Per modificare l'ordine degli utilizzi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Ad esempio, per modificare l'ordine da "Stati Uniti e Canada" prima e "Internazionale" secondo all'ordine inverso:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La priorità per le route vocali "Altre +1" e "Internazionali" viene assegnata automaticamente. Non hanno importanza se hanno priorità inferiori rispetto a "Redmond 1" e "Redmond 2".

## <a name="example-2-configuration-steps"></a>Esempio 2: Passaggi di configurazione

L'esempio seguente mostra come:

1. Creare un nuovo utilizzo PSTN denominato Internazionale.
2. Creare una nuova route vocale denominata Internazionale.
3. Creare un criterio di routing vocale denominato Nessuna restrizione.
4. Assegnare il criterio all'utente John Woods.

È possibile usare [l'Microsoft Teams di amministrazione o](#admincenterexample2) [PowerShell](#powershellexample2) per eseguire questa procedura.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: Creare l'utilizzo PSTN "internazionale"

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing e quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**
2. Fare **clic su Aggiungi**, digitare **Internazionale** e quindi fare clic su **Applica.**

#### <a name="step-2-create-the-international-voice-route"></a>Passaggio 2: Creare la route vocale "Internazionale"

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Routing** vocale diretto e quindi  >  selezionare la **scheda Route** vocali.
2. Fare **clic su** Aggiungi, immettere "Internazionale" come nome e quindi aggiungere la descrizione.
3. Impostare la priorità su 4 e quindi impostare lo schema di numeri composto su \d+.
4. In **SBC registrati (facoltativo)** fare clic su **Aggiungi SBC,** selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **Applica**.
5. In **Record di utilizzo PSTN (facoltativo)** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Internazionale" e quindi fare clic su **Applica.**
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione" e aggiungere al criterio gli utilizzi PSTN "Stati Uniti e Canada" e "Internazionali"

L'utilizzo PSTN "Stati Uniti e Canada" viene riutilizzato in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare **a** Criteri di  >  **routing vocale** e quindi fare clic su **Aggiungi.**
2. Digitare **No Restrictions** come nome e aggiungere una descrizione.
3. In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "Internazionale". Fare clic **su Applica**.

    Prendere nota dell'ordine di utilizzo pstn:

    - Se una chiamata effettuata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come in questo esempio, la chiamata segue il percorso impostato nell'utilizzo "Stati Uniti e Canada" e viene applicata la logica di routing speciale. In altre informazioni, la chiamata viene instradata sbc1.contoso.biz e sbc2.contoso.biz e quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.

    - Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.

4. Fare clic su **Salva**.

Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Passaggio 4: Assegnare i criteri di routing vocale a un utente denominato John Woods

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare **clic su** Criteri e quindi accanto a Criteri **assegnati** fare clic su **Modifica.**
3. In **Criteri routing vocale** selezionare il criterio "Nessuna restrizione" e quindi fare clic su **Salva.**

Il risultato è che i criteri vocali applicati alle chiamate di John Woods sono senza restrizioni e seguiranno la logica del routing delle chiamate disponibile per le chiamate usa, canada e internazionali.

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: Creare l'utilizzo PSTN "internazionale"

In una sessione remota di PowerShell in Skype for Business Online immettere:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Passaggio 2: Creare una nuova route vocale denominata "Internazionale"

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

L'utilizzo PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate ai numeri "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Prendere nota dell'ordine di utilizzo pstn:

  - Se una chiamata effettuata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come nell'esempio seguente, la chiamata segue la route impostata nell'utilizzo "Stati Uniti e Canada" e viene applicata la logica di routing speciale. In altre informazioni, la chiamata viene instradata sbc1.contoso.biz e sbc2.contoso.biz e quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.

  - Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing. Immettere il comando:

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

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Passaggio 4: Assegnare i criteri di routing vocale all'utente denominato John Woods

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Verificare quindi l'attività usando il comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Che restituisce:

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

Il risultato è che il criterio vocale applicato alle chiamate di John Woods è senza restrizioni e seguirà la logica del routing delle chiamate disponibile per le chiamate negli Stati Uniti, in Canada e in Internazionali.

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
