---
title: Configurare il routing vocale per l'instradamento diretto
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
description: Scopri come configurare il routing vocale con l'instradamento diretto del sistema telefonico Microsoft.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530993"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Configurare il routing vocale per l'instradamento diretto

Questo articolo descrive come configurare il routing vocale per l'instradamento diretto del sistema telefonico.  Questo è il passaggio 3 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Collegare il servizio SBC al Sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3. Configurare il routing vocale** (questo articolo)
- Passaggio 4. [Convertire i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)

## <a name="voice-routing-overview"></a>Panoramica del routing vocale

Il Sistema telefonico Microsoft dispone di un meccanismo di instradamento che consente l'invio di una chiamata a uno specifico controller dei confini della sessione (SBC) in base a: 

- Schema numero definito 
- Lo schema dei numeri più l'utente specifico che effettua la chiamata
 
I file SBC possono essere designati come attivi e come backup. Quando il servizio SBC configurato come attivo non è disponibile per un percorso di chiamata specifico, la chiamata verrà instradata a un SBC di backup.
 
Il routing vocale è costituito da questi elementi: 

- **Criteri di routing vocale:** contenitore per l'utilizzo di PSTN, che può essere assegnato a un utente o a più utenti. 

- **Utilizzi di PSTN:** contenitore per i percorsi vocali e l'utilizzo di PSTN, che può essere condiviso in criteri di routing vocale diversi. 

- **Percorsi vocali:** un modello di numero e un set di gateway PSTN online da usare per le chiamate in cui il numero di chiamata corrisponde a quello specificato.

- **Gateway PSTN online:** puntatore a un database SBC che archivia anche la configurazione applicata quando una chiamata viene inserita tramite SBC, ad esempio l'inoltro PAI (Forward P-Asserted-Identity) o Codec preferiti; possono essere aggiunti ai percorsi vocali.

## <a name="voice-routing-policy-considerations"></a>Considerazioni sui criteri di routing vocale

Se un utente dispone di una licenza per un Piano per chiamate, le chiamate in uscita vengono automaticamente indirizzate attraverso l'infrastruttura PSTN del Piano per chiamate Microsoft. Se si configura e si assegna un criterio di instradamento vocale online a un utente di un Piano per chiamate, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composto corrisponde a uno schema di numero definito nel criterio di routing vocale online. Se esiste una corrispondenza, la chiamata viene instradata attraverso il trunk di instradamento diretto. Se non ci sono corrispondenze, la chiamata viene instradata attraverso l'infrastruttura PSTN del Piano per chiamate.

> [!CAUTION]
> Se si configura e si applica il criterio di routing vocale online globale (impostazione predefinita a livello di organizzazione), tutti gli utenti abilitati alla voce nell'organizzazione erediteranno tale criterio, il che potrebbe comportare l'instradamento accidentale delle chiamate PSTN da parte di utenti del Piano per chiamate a un trunk di routing diretto. Se non si vuole che tutti gli utenti usino i criteri di routing vocale online globale, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per i comandi vocali.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Esempio 1: Routing vocale con un utilizzo di PSTN

Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso delle chiamate.

**Flusso delle chiamate 1 (a sinistra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non sbc1.contoso.biz né sbc2.contoso.biz disponibili, la chiamata viene interrotta. 

**Flusso delle chiamate 2 (a destra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene prima instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se nessun SBC è disponibile, verrà tentato il percorso con priorità più bassa (sbc3.contoso.biz e sbc4.contoso.biz). Se nessuno degli SBC è disponibile, la chiamata viene interrotta. 

![Mostra esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In entrambi gli esempi, mentre alle route vocali sono assegnate priorità, i percorsi vengono provati in ordine casuale. Quando due SBC sono configurati in un'unica route, il traffico di rete deve essere instradabile tra SBC o il supporto non verrà stabilito sui trasferimenti, perché è possibile che il nuovo invito per il trasferimento sia inviato a un altro SBC della route.

  > [!NOTE]
  > A meno che l'utente non abbia anche una licenza per un Piano per chiamate Microsoft, le chiamate a qualsiasi numero tranne i numeri corrispondenti ai modelli +1 425 XXX XX XX o +1 206 XXX XX XX nella configurazione di esempio vengono eliminate. Se l'utente dispone di una licenza per un Piano per chiamate, la chiamata viene automaticamente instradata in base ai criteri del Piano per chiamate Microsoft. Il Piano per chiamate Microsoft si applica automaticamente come ultimo percorso a tutti gli utenti con licenza Piano per chiamate Microsoft e non richiede una configurazione aggiuntiva di instradamento delle chiamate.

Nell'esempio mostrato nella figura seguente viene aggiunto un percorso vocale per inviare chiamate a tutti gli altri numeri degli Stati Uniti e di Canada (chiamate indirizzate al cosiddetto modello di numero +1 XXX XXX XX XX).

![Mostra i criteri di instradamento vocale con una terza route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Per tutte le altre chiamate, se un utente dispone di entrambe le licenze (Sistema telefonico Microsoft e Piano per chiamate Microsoft), viene utilizzato il percorso automatico. Se nessun elemento corrisponde ai modelli di numerazione nei percorsi vocali online creati dall'amministratore, la chiamata viene instradata attraverso il Piano per chiamate Microsoft. Se l'utente ha solo Sistema telefonico Microsoft, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.

  > [!NOTE]
  > Il valore Priorità per la route "Altro +1" non è importante in questo caso perché esiste una sola route che corrisponde al modello +1 XXX XXX XX XX. Se un utente effettua una chiamata a +1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene interrotta.

La tabella seguente riepiloga la configurazione usando tre route vocali. In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo di PSTN, "STATI UNITI e Canada".  Tutte le route sono associate all'utilizzo di PSTN "Stati Uniti e Canada" e l'utilizzo di PSTN è associato ai criteri di routing vocale "Solo Stati Uniti".

|**Utilizzo PSTN**|**Route vocale**|**Schema numerico**|**Priorità**|**SBC**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Percorso attivo per i numeri +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route per i numeri +1 XXX XXX XX XX (eccetto +1 425 XXX XX XX o +1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Esempio 1: Passaggi di configurazione

L'esempio seguente mostra come:

1. Creare un singolo utilizzo di PSTN.
2. Configurare tre percorsi vocali.
3. Creare un criterio di routing vocale.
4. Assegnare il criterio a un utente denominato Low.

Per eseguire queste operazioni, è [possibile usare](#admincenterexample1) l'interfaccia di amministrazione di Microsoft Teams o [PowerShell.](#powershellexample1)

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: Creare l'utilizzo di PSTN "Stati Uniti e Canada"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing, quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**
2. Fare **clic su** Aggiungi, digitare US e **Canada,** quindi fare clic su **Applica.**

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: Creare tre percorsi vocali (Redmond 1, Redmond 2 e Other +1)

I passaggi seguenti descrivono come creare un percorso vocale. Seguire questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e Other +1 per questo esempio usando le impostazioni descritte nella tabella precedente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Instradamento diretto  >  **vocale,** quindi seleziona la **scheda Percorsi** vocali.
2. Fare **clic su** Aggiungi, quindi immettere un nome e una descrizione per il percorso vocale.
3. Impostare la priorità e specificare il modello dei numeri componiti.
4. Per registrare un SBC con il percorso vocale, in SBC registrati **(facoltativo)** fare clic su Aggiungi **SBC,** selezionare gli SBC da registrare e quindi fare clic su **Applica.**
5. Per aggiungere record di utilizzo PSTN (facoltativo), in Record di utilizzo **PSTN fare** clic su Aggiungi utilizzo **PSTN,** selezionare i record PSTN da aggiungere e quindi fare clic su **Applica.**
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo di PSTN "Stati Uniti e Canada" ai criteri

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Criteri  >  **di instradamento vocale,** quindi fai clic su **Aggiungi.**
2. Digitare **solo US** come nome e aggiungere una descrizione.
3. In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **Applica.**
4. Fare clic su **Salva**.

Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: Assegnare il criterio di instradamento vocale a un utente denominato Basso

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare **clic su** Criteri e quindi su Modifica accanto a **Criteri** **assegnati.**
3. In **Criteri di routing vocale** selezionare il criterio "Solo Stati Uniti" e quindi fare clic su **Salva.**

Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: Creare l'utilizzo di PSTN "Stati Uniti e Canada"

In una sessione remota di PowerShell in Skype for Business online digita:

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

L'esempio seguente mostra il risultato dell'esecuzione del comando di Powershell per visualizzare i nomi completi `(Get-CSOnlinePSTNUsage).usage` (non troncati):

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: Creare tre percorsi vocali (Redmond 1, Redmond 2 e Other +1)

Per creare il percorso "Redmond 1", in una sessione di PowerShell in Skype for Business online, immetti:

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

Per creare il percorso di Redmond 2, immetti:

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
  > Verificare che l'espressione regolare nell'attributo NumberAttribute sia un'espressione valida. È possibile testarlo usando questo sito Web: [https://www.regexpal.com](https://www.regexpal.com)

In alcuni casi è necessario instradare tutte le chiamate allo stesso SBC; use -NumberNumerazione ".*"

Instradare tutte le chiamate allo stesso SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Verificare di aver configurato correttamente la route eseguendo il comando `Get-CSOnlineVoiceRoute` di PowerShell usando le opzioni indicate:

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

Nell'esempio, al percorso "Altro +1" è stata assegnata automaticamente la priorità 4. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo di PSTN "Stati Uniti e Canada" ai criteri

In una sessione di PowerShell in Skype for Business online digita:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Il risultato è illustrato nell'esempio seguente:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: Assegnare il criterio di instradamento vocale a un utente denominato Basso

In una sessione di PowerShell in Skype for Business online digita:

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

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Esempio 2: Routing vocale con più utilizzi di PSTN

Il criterio di instradamento vocale creato nell'esempio 1 consente solo chiamate a numeri di telefono negli Stati Uniti e in Canada, a meno che all'utente non sia assegnata anche la licenza del Piano per chiamate Microsoft.

Nell'esempio seguente è possibile creare il criterio di routing vocale "Nessuna restrizione". I criteri riutilizzano l'utilizzo di PSTN "Stati Uniti e Canada" creato nell'esempio 1, nonché il nuovo utilizzo di PSTN "internazionale". Questo criterio indirizza tutte le altre chiamate agli SBC sbc2.contoso.biz e sbc5.contoso.biz.

Gli esempi riportati di seguito assegnano il criterio Solo stati Uniti all'utente Low per gli Stati Uniti e il criterio Nessuna restrizione all'utente John Foresta, in modo che il routing si verifichi nel modo seguente:

- Basso degli Stati Uniti - Politica solo per gli Stati Uniti.  Le chiamate sono consentite solo ai numeri degli Stati Uniti e dei Canada. Quando si chiama all'intervallo dei numeri di Redmond, è necessario utilizzare il set specifico di numeri SBC. I numeri non statunitensi verranno instradati solo se all'utente non viene assegnata la licenza del Piano per chiamate.

- John Rieti - Politica internazionale.  Le chiamate sono consentite a qualsiasi numero. Quando si chiama all'intervallo dei numeri di Redmond, è necessario utilizzare il set specifico di numeri SBC. I numeri non statunitensi verranno instradati sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra i criteri di routing vocale assegnati all'utente Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Per tutte le altre chiamate, se un utente dispone di entrambe le licenze (Sistema telefonico Microsoft e Piano per chiamate Microsoft), viene utilizzato il percorso automatico. Se nessun elemento corrisponde ai modelli di numerazione nei percorsi vocali online creati dall'amministratore, la chiamata viene instradata utilizzando il Piano per chiamate Microsoft.  Se l'utente ha solo il Sistema telefonico Microsoft, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.

![Mostra i criteri di instradamento vocale assegnati all'utente John Più di unirsi](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

La tabella seguente riepiloga le designazioni di utilizzo e i percorsi vocali del criterio di routing "Nessuna restrizione". 

|**Utilizzo PSTN**|**Route vocale**|**Schema numerico**|**Priorità**|**SBC**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Percorso attivo per i numeri del chiamato +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri del chiamato +1 425 XXX XX XX o +1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Percorso per i numeri del chiamato +1 XXX XXX XX XX (eccetto +1 425 XXX XX XX o +1 206 XXX XX XX)|
|Internazionale|Internazionale|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route per qualsiasi schema di numerazione |

  > [!NOTE]
  > - L'ordine di utilizzo di PSTN nei criteri di routing vocale è fondamentale. Gli utilizzi vengono applicati in ordine e, se viene trovata una corrispondenza nel primo utilizzo, gli altri utilizzi non vengono mai valutati. L'utilizzo di PSTN "internazionale" deve essere posizionato dopo l'utilizzo di PSTN "Stati Uniti e Canada". Per modificare l'ordine di utilizzo di PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Ad esempio, per cambiare l'ordine da "Stati Uniti e Canada" per primo e "Internazionale" secondo all'ordine inverso:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La priorità per i percorsi vocali "Altri +1" e "Internazionali" viene assegnata automaticamente. Non importa se hanno priorità inferiori rispetto a "Redmond 1" e "Redmond 2".

## <a name="example-2-configuration-steps"></a>Esempio 2: Passaggi di configurazione

L'esempio seguente mostra come:

1. Creare un nuovo utilizzo di PSTN denominato Internazionale.
2. Creare un nuovo percorso vocale chiamato Internazionale.
3. Creare un criterio di routing vocale denominato Nessuna restrizione.
4. Assegnare il criterio all'utente John Piùele.

Per eseguire queste operazioni, è [possibile usare](#admincenterexample2) l'interfaccia di amministrazione di Microsoft Teams o [PowerShell.](#powershellexample2)

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: Creare l'utilizzo di PSTN "internazionale"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing, quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**
2. Fare **clic su** Aggiungi, digitare **Internazionale** e quindi fare clic su **Applica.**

#### <a name="step-2-create-the-international-voice-route"></a>Passaggio 2: Creare il percorso vocale "Internazionale"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Instradamento diretto  >  **vocale,** quindi seleziona la **scheda Percorsi** vocali.
2. Fare **clic** su Aggiungi, immettere "Internazionale" come nome e quindi aggiungere la descrizione.
3. Impostare la priorità su 4, quindi impostare il modello di numero composto su \d+.
4. In **SBC registrati (facoltativo)** fare clic su Aggiungi **SBC,** selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **Applica.**
5. In **Record di utilizzo PSTN (facoltativo)** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Internazionale" e quindi fare clic su **Applica.**
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione" e aggiungere al criterio gli utilizzi di PSTN "Stati Uniti e Canada" e "Internazionali"

L'utilizzo di PSTN "STATI UNITI e Canada" viene riutilizzato in questo criterio di routing vocale per mantenere una gestione speciale delle chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Criteri  >  **di instradamento vocale,** quindi fai clic su **Aggiungi.**
2. Digitare **No Restrictions** come nome e aggiungere una descrizione.
3. In Record di utilizzo **PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "Internazionale". Fare clic **su Applica.**

    Prendere nota dell'ordine di utilizzo di PSTN:

    - Se viene effettuata una chiamata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come in questo esempio, la chiamata segue il percorso impostato per l'utilizzo in "Stati Uniti e Canada" e viene applicata la logica di routing speciale. In altre caso, la chiamata viene instradata usando sbc1.contoso.biz e sbc2.contoso.biz, quindi sbc3.contoso.biz e sbc4.contoso.biz come percorsi di backup.

    - Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.

4. Fare clic su **Salva**.

Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Passaggio 4: Assegnare il criterio di routing vocale a un utente di nome Luca Agnesi

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare **clic su** Criteri e quindi su Modifica accanto a **Criteri** **assegnati.**
3. In **Criteri di routing vocale** selezionare il criterio "Nessuna restrizione" e quindi fare clic su **Salva.**

Il risultato è che il criterio vocale applicato alle chiamate di John Eseguo è illimitato e seguirà la logica del routing delle chiamate disponibile per le chiamate negli Stati Uniti, in Canada e all';internazionale.

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: Creare l'utilizzo di PSTN "internazionale"

In una sessione remota di PowerShell in Skype for Business online, immetti:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Passaggio 2: Creare un nuovo percorso vocale denominato "Internazionale"

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

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione"

I servizi PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale delle chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Prendere nota dell'ordine di utilizzo di PSTN:

  - Se viene effettuata una chiamata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come nell'esempio seguente, la chiamata segue il percorso impostato per l'utilizzo in "Stati Uniti e Canada" e viene applicata la logica di routing speciale. In altre caso, la chiamata viene instradata usando sbc1.contoso.biz e sbc2.contoso.biz, quindi sbc3.contoso.biz e sbc4.contoso.biz come percorsi di backup.

  - Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing. Immettere il comando:

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

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Passaggio 4: Assegnare i criteri di instradamento vocale all'utente John Piùle

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Verificare quindi l'attività usando il comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Che restituisce:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

Il risultato è che il criterio vocale applicato alle chiamate di John Eseguo è illimitato e seguirà la logica del routing delle chiamate disponibile per le chiamate negli Stati Uniti, in Canada e all';internazionale.

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
