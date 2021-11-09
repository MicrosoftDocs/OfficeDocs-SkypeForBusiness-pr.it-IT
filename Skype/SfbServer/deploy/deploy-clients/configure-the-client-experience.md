---
title: Configurare l'esperienza client con Skype for Business 2015
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
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'esperienza client per Skype for Business utenti."
ms.openlocfilehash: d1baa06558f7f3dcc4829d1e03c387e9ab54fa32
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845979"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurare l'esperienza client con Skype for Business 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'esperienza client per Skype for Business 2015.
  
Skype for Business 2015 offre una nuova esperienza utente basata sull'esperienza Skype prodotto consumer. Oltre a tutte le funzionalità di Lync, Skype for Business nuove funzionalità con controlli semplificati e icone familiari. Per informazioni dettagliate sulla nuova esperienza client, vedere [Explore Skype for Business.](https://go.microsoft.com/fwlink/?LinkId=529022)
  
Skype for Business Server supporta la nuova esperienza Skype for Business client e l'esperienza client Lync. Gli amministratori possono scegliere l'esperienza client preferita per gli utenti. Ad esempio, è possibile distribuire l'esperienza client Lync fino a quando gli utenti dell'organizzazione non hanno una formazione completa nella nuova esperienza Skype for Business utente. In caso contrario, se non sono stati ancora aggiornati tutti gli utenti a Skype for Business Server, è consigliabile che tutti gli utenti abbiano la stessa esperienza client finché non vengono aggiornati tutti al nuovo server.
  
> [!IMPORTANT]
> Se nell'organizzazione sono distribuiti Skype for Business Server e Lync Server, l'esperienza client predefinita varia a seconda delle versioni del server e delle impostazioni dell'interfaccia utente. Quando gli utenti avviano Skype for Business per la prima volta, visualizzano sempre l'interfaccia Skype for Business utente, anche se è stata selezionata l'esperienza client Lync. Dopo alcuni minuti, agli utenti viene richiesto di passare alla modalità Lync. Per ulteriori informazioni, vedere **First launch client behavior** più avanti in questo argomento.
  
> [!NOTE]
> L'esperienza client lync 2013 non è un'opzione per Skype for Business versioni client 2016 o successive. Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per assicurarsi che non inizi con il numero 16. ad esempio: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurare l'esperienza client

È possibile specificare l'esperienza client che gli utenti dell'organizzazione potranno visualizzare utilizzando il cmdlet **Set-CSClientPolicy** con il parametro EnableSkypeUI:
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

dove XdsIdentity fa riferimento al criterio globale o a un criterio sito denominato.
  
Il comando seguente consente di selezionare l'Skype for Business client per tutti gli utenti dell'organizzazione interessati dal criterio globale (ricordare che i criteri specifici del sito o dell'utente hanno la precedenza sul criterio globale): 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

Il comando successivo consente di selezionare l'esperienza client Lync per tutti gli utenti dell'organizzazione interessati dal criterio globale:
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

Il comando successivo seleziona l'Skype for Business client per tutti gli utenti all'interno del sito Redmond:
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Se si desidera configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente utilizzando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici utilizzando il cmdlet **Grant-CsClientPolicy.**
  
Ad esempio, il comando seguente crea un nuovo criterio client, SalesClientUI, che seleziona l'Skype for Business client:
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

Il comando successivo assegna il criterio SalesClientUI a tutti i membri del reparto Vendite:
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamenti client per il primo avvio

Per impostazione predefinita, quando gli utenti avviano Skype for Business 2015 per la prima volta, visualizzano sempre l'interfaccia utente di Skype for Business, anche se è stata selezionata l'esperienza client Lync impostando il valore del parametro EnableSkypeUI su $False come descritto in precedenza. Dopo alcuni minuti, agli utenti verrà chiesto di passare alla modalità Lync.
  
Se si desidera visualizzare l'interfaccia utente di Lync quando gli utenti avviano il client Skype for Business per la prima volta, eseguire la procedura seguente prima che il client venga avviato per la prima volta dopo l'aggiornamento:
  
1. Verificare che il valore di sia impostato su $False nel criterio  `EnableSkypeUI` in uso come descritto in precedenza.
    
2. Aggiornare il Registro di sistema nel computer dell'utente. È consigliabile eseguire questa operazione prima che gli utenti avviino per la prima volta Skype for Business client ed è consigliabile eseguire questa operazione una sola volta. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer aggiunto a un dominio, vedere la sezione più avanti nell'argomento.
    
    Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** crea un nuovo **valore Binary.**
    
    Il **nome del** valore deve essere **EnableSkypeUI** e i dati **valore** devono essere impostati su **00 00 00 00 00**.
    
    La chiave dovrebbe essere simile alla seguente:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

L'interfaccia utente di Lync verrà ora visualizzata quando gli utenti avviano Skype for Business client per la prima volta.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controllare la visualizzazione dell'esercitazione sulla schermata iniziale

Quando gli utenti aprono il client Skype for Business, il comportamento predefinito prevede la visualizzazione di una schermata iniziale che include 7 suggerimenti rapidi che la maggior parte *delle persone richiede.* È possibile disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:
  
Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** crea un nuovo **valore DWORD (32 bit).** Il **nome del** valore deve essere **IsBasicTutorialSeenByUser** e i dati **value** devono essere impostati su **1.**
  
La chiave dovrebbe essere simile alla seguente:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Disattivare l'esercitazione sul client

Se non si desidera che gli utenti possano accedere all'esercitazione, è possibile disattivare l'esercitazione client con il valore del Registro di sistema seguente:
  
Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** crea un nuovo **valore DWORD (32 bit).** Il **nome valore** deve essere **TutorialFeatureEnabled** e i dati **value** devono essere impostati su **0.**
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

Puoi riattivare l'esercitazione impostando i **dati valore** su **1.**
  
## <a name="default-client-behaviors"></a>Comportamenti client predefiniti

Se nell'organizzazione sono distribuiti Skype for Business Server e Lync Server, l'esperienza client varia a seconda delle versioni del server e dell'Skype'interfaccia utente. La tabella seguente mostra l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:
  

|**Versione server**|**Impostazione EnableSkypeUI**|**Esperienza client**|
|:-----|:-----|:-----|
|Skype for Business Server |Predefinita  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Vero  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Falso  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for Business in un secondo momento se si modifica l'impostazione dell'interfaccia utente $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con patch corrette)  <br/> |Predefinita  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for Business in un secondo momento se si modifica l'impostazione dell'interfaccia utente $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con patch corrette)  <br/> |Vero  <br/> |Skype for Business  <br/> |
|Lync Server 2010 o Lync Server 2013 (con patch corrette)  <br/> |Falso  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for Business in un secondo momento se si modifica l'impostazione dell'interfaccia utente $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (senza patch)  <br/> |Predefinita  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente non può passare Skype for Business successivo)  <br/> |
   
La tabella seguente mostra l'esperienza client quando l'amministratore modifica l'impostazione iniziale per l'esperienza Skype'interfaccia utente:
  

|**Versione server**|**Impostazione EnableSkypeUI**|**Interfaccia utente client = Lync**|**Interfaccia utente client = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |Vero  <br/> |L'utente ha chiesto di passare a Skype for Business  <br/> |Skype for Business  <br/> |
|Skype for Business Server |Falso  <br/> |Modalità Lync  <br/> |L'utente ha chiesto di passare alla modalità Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (con patch corrette)  <br/> |Vero  <br/> |L'utente ha chiesto di passare a Skype for Business  <br/> |Skype for Business  <br/> |
|Lync Server 2010 o Lync Server 2013 (con patch corrette)  <br/> |Falso  <br/> |Modalità Lync  <br/> |L'utente ha chiesto di passare alla modalità Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (senza patch)  <br/> |Predefinita  <br/> |Modalità Lync (non è possibile passare a Skype for Business)  <br/> |Modalità Lync (non è possibile passare a Skype for Business)  <br/> |
   
Le versioni della patch necessarie per gestire la configurazione del client Skype for Business client sono:
  
- Lync Server 2010 - Aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per Lync Server 2010. Per informazioni, vedere [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - Aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per Lync Server 2013. Per informazioni, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer aggiunto a un dominio

L'aggiornamento del Registro di sistema per visualizzare l'esperienza del client Lync al primo avvio del client Skype for Business 2015 deve essere eseguito una sola volta. Se si utilizza un oggetto Criteri di gruppo per aggiornare il Registro di sistema, è necessario definire l'oggetto per creare un nuovo valore anziché aggiornare i dati value. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposta i dati valore su 0. 
  
Nella procedura seguente viene descritto come modificare il Registro di sistema in modo che l'esperienza client Lync sia visualizzata la prima volta che un utente avvia il client Skype for Business 2015. È inoltre possibile utilizzare questa procedura per aggiornare il Registro di sistema per disabilitare l'esercitazione sulla schermata iniziale come descritto in precedenza.
  
### <a name="to-create-the-gpo"></a>Per creare l'oggetto Criteri di gruppo

1. Avviare la **console Gestione Criteri di gruppo.**
    
    Per informazioni su come utilizzare Console Gestione Criteri di gruppo, vedere [Console Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))
    
2. Fare clic con il pulsante destro **del mouse** sul nodo Oggetti Criteri di gruppo e **scegliere Nuovo** dal menu.
    
3. Nella finestra **di dialogo Nuovo oggetto** Criteri di gruppo immettere un nome per l'oggetto Criteri di gruppo, ad esempio MakeLyncDefaultUI, e quindi fare clic su **OK.**
    
4. Fai clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo appena creato e scegli **Modifica** dal menu.
    
5. **Nell'Editor Gestione Criteri di gruppo** espandere Configurazione **utente,** **Preferenze,** espandere **Windows Impostazioni** e quindi selezionare il nodo **Registro di** sistema.
    
6. Fare clic con il pulsante destro del mouse sul nodo **Registro** di sistema e quindi **scegliere Nuovo elemento** del Registro di  >  **sistema**.
    
7. Nella finestra **di dialogo Nuove proprietà del Registro** di sistema aggiornare quanto segue:
    
   |**Campo**|**Valore da selezionare o immettere**|
   |:-----|:-----|
   |**Azione** <br/> |**Creare** <br/> |
   |**Hive** <br/> | HKEY_CURRENT_USER <br/> |
   |**Percorso chiave** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nome valore** <br/> |EnableSkypeUI  <br/> |
   |**Tipo valore** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. Fare **clic su OK** per salvare le modifiche e quindi chiudere l'oggetto Criteri di gruppo.
    
Sarà quindi necessario collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui si desidera assegnare il criterio, ad esempio un'unità organizzativa.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Per utilizzare l'oggetto Criteri di gruppo per assegnare il criterio

1. Nella Console Gestione Criteri di gruppo fare clic con il pulsante destro del mouse sull'unità organizzativa a cui si desidera assegnare il criterio e quindi scegliere **Collega a un oggetto Criteri di gruppo esistente.**
    
2. Nella finestra **di dialogo Seleziona oggetto** Criteri di gruppo selezionare l'oggetto Criteri di gruppo creato e quindi fare clic su **OK.**
    
3. Nel computer dell'utente di destinazione, aprire un prompt dei comandi e digitare il comando seguente:
       
   ```console
   pupdate /target:user
   ```
     Il messaggio "Aggiornamento dei criteri..." viene visualizzato mentre viene applicato l'oggetto Criteri di gruppo. Al termine, viene visualizzato il messaggio "Aggiornamento dei criteri utente completato".
    
4. Al prompt dei comandi, digitare il seguente comando:
    
    **gpresult /r**
    
    Di seguito viene visualizzato "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.
    
È inoltre possibile verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema. Aprire l'editor del Registro di sistema e passare alla chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].** Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, verrà visualizzato un valore denominato EnableSkypeUI con un valore pari a 0.
