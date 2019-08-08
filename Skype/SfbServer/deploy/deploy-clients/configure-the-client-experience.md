---
title: Configurare l'esperienza client con Skype for business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for business."
ms.openlocfilehash: ea1d38693291ebfa7d7cc4f8893b0aa6ec1c0d83
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234453"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurare l'esperienza client con Skype for business 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for business 2015.
  
Skype for business 2015 offre una nuova esperienza utente basata sull'esperienza di prodotto consumer Skype. Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone note. Per informazioni dettagliate sulla nuova esperienza client, vedere [esplorare Skype for business](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype for Business Server supporta la nuova esperienza client Skype for business e l'esperienza client Lync. Come amministratore, puoi scegliere l'esperienza client preferita per gli utenti. Ad esempio, potresti voler distribuire l'esperienza del client Lync fino a quando gli utenti dell'organizzazione non saranno completamente formati nella nuova esperienza di Skype for business. In alternativa, se non hai ancora aggiornato tutti gli utenti a Skype for Business Server, potresti volere che tutti gli utenti abbiano la stessa esperienza client finché tutti non vengono aggiornati nel nuovo server.
  
> [!IMPORTANT]
> Se l'organizzazione ha implementato sia Skype for Business Server che Lync Server, l'esperienza client predefinita sarà diversa a seconda delle versioni del server e delle impostazioni dell'interfaccia utente. Quando gli utenti lanciano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se hai selezionato l'esperienza del client Lync. Dopo alcuni minuti, agli utenti viene chiesto di passare alla modalità Lync. Per altre informazioni, vedere **prima** di tutto avviare il comportamento del client più avanti in questo argomento.
  
> [!NOTE]
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client Skype for business 2016 o versione successiva. Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurare l'esperienza client

Puoi specificare l'esperienza client che gli utenti dell'organizzazione vedranno usando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

dove XdsIdentity si riferisce al criterio globale o a un criterio del sito denominato.
  
Il comando seguente seleziona l'esperienza del client Skype for business per tutti gli utenti dell'organizzazione interessati dal criterio globale (Ricordati che i criteri per il sito o i criteri specifici dell'utente sostituiscono il criterio globale): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

Il comando successivo seleziona l'esperienza client Lync per tutti gli utenti dell'organizzazione interessati dal criterio globale:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

Il comando successivo seleziona l'esperienza client Skype for business per tutti gli utenti all'interno del sito Redmond:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Se si vuole configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente usando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici tramite **Grant-CsClientPolicy** cmdlet.
  
Ad esempio, il comando seguente crea un nuovo criterio client, SalesClientUI, che seleziona l'esperienza del client Skype for business:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

Il comando successivo assegna il criterio SalesClientUI a tutti i membri del reparto vendite:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamenti del client al primo avvio

Per impostazione predefinita, quando gli utenti avviano Skype for business 2015 per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'esperienza client di Lync impostando il valore del parametro EnableSkypeUI su $False come descritto precedentemente. Dopo alcuni minuti, all'utente verrà richiesto di passare alla modalità Lync.
  
Se desideri visualizzare l'interfaccia utente di Lync al primo avvio del client Skype for Business da parte dell'utente, segui questa procedura prima che il client venga avviato per la prima volta in seguito all'aggiornamento:
  
1. Verificare che il valore di `EnableSkypeUI` sia impostato su $false nel criterio in uso come descritto in precedenza.
    
2. Aggiorna il Registro di sistema nel computer dell'utente. Esegui l'operazione una sola volta, prima del primo avvio del client Skype for Business da parte dell'utente. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer che fa parte di un dominio, vedi la sezione presente successivamente nell'argomento.
    
    Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** creare un nuovo valore **binario** .
    
    **Nome valore** deve essere **EnableSkypeUI**, mentre **Dati valore** deve essere impostato su **00 00 00 00**.
    
    La chiave dovrebbe avere un aspetto simile al seguente:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

L'interfaccia utente di Lync verrà visualizzata al primo avvio del client Skype for Business da parte dell'utente.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controllare la visualizzazione dell'esercitazione nella schermata iniziale

Quando gli utenti aprono il client Skype for business, il comportamento predefinito prevede la visualizzazione di una schermata iniziale che include *7 suggerimenti veloci che la maggior parte delle persone richiede*. Puoi disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:
  
Nella chiave **[HKEY_CURRENT_USER\software\microsoft\office\15.0\Lync]** creare un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **IsBasicTutorialSeenByUser**, mentre **Dati valore** deve essere impostato su **1**.
  
La chiave dovrebbe avere un aspetto simile al seguente:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Disattivare l'esercitazione nel client

Se non vuoi che gli utenti siano in grado di accedere all'esercitazione, puoi disattivare l'esercitazione nel client con il seguente valore del Registro di sistema:
  
Nella chiave **[HKEY_CURRENT_USER\software\microsoft\office\15.0\Lync]** creare un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **TutorialFeatureEnabled**, mentre **Dati valore** deve essere impostato su **0**.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Puoi riattivare l'esercitazione impostando **Dati valore** su **1**.
  
## <a name="default-client-behaviors"></a>Comportamenti client predefiniti

Se l'organizzazione ha implementato sia Skype for Business Server che Lync Server, l'esperienza del client sarà diversa a seconda delle versioni del server e dell'impostazione dell'interfaccia utente Skype. La tabella seguente mostra l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:
  

|**Versione del server**|**Impostazione EnableSkypeUI**|**Esperienza client**|
|:-----|:-----|:-----|
|Skype for Business Server |Predefinita  <br/> |Skype for business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for business  <br/> |
|Skype for Business Server  |False  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |Predefinita  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |True  <br/> |Skype for business  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |False  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (senza patch)  <br/> |Predefinita  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente non può passare a Skype for business in seguito)  <br/> |
   
La tabella seguente mostra l'esperienza del client quando l'amministratore cambia l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:
  

|**Versione del server**|**Impostazione EnableSkypeUI**|**Interfaccia utente client = Lync**|**Interfaccia utente client = Skype for business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |L'utente ha chiesto di passare a Skype for business  <br/> |Skype for business  <br/> |
|Skype for Business Server |False  <br/> |Modalità Lync  <br/> |L'utente ha chiesto di passare alla modalità Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |True  <br/> |L'utente ha chiesto di passare a Skype for business  <br/> |Skype for business  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |False  <br/> |Modalità Lync  <br/> |L'utente ha chiesto di passare alla modalità Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (senza patch)  <br/> |Predefinita  <br/> |Modalità Lync (non è possibile passare a Skype for business)  <br/> |Modalità Lync (non è possibile passare a Skype for business)  <br/> |
   
Le versioni di patch necessarie per gestire la configurazione del client Skype for business sono:
  
- Lync Server 2010-aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per Lync Server 2010. Per informazioni, vedere [aggiornamenti per Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per Lync Server 2013. Per informazioni, vedere [aggiornamenti per Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer che fa parte di un dominio

L'aggiornamento del registro di sistema per visualizzare l'esperienza del client Lync la prima volta che un utente avvia il client Skype for business 2015 deve essere eseguita una sola volta. Se usi un oggetto Criteri di gruppo per aggiornare il Registro di sistema, devi definire l'oggetto per creare un nuovo valore anziché aggiornare Dati valore. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposterà Dati valore su 0. 
  
La procedura seguente descrive come modificare il registro di sistema in modo che l'esperienza del client Lync venga visualizzata la prima volta che un utente avvia il client Skype for business 2015. Puoi inoltre utilizzare questa procedura per aggiornare il Registro di sistema e disabilitare l'esercitazione nella schermata iniziale come descritto in precedenza.
  
### <a name="to-create-the-gpo"></a>Per creare l'oggetto Criteri di gruppo

1. Avvia la **Console Gestione Criteri di gruppo**.
    
    Per informazioni su come usare la Console Gestione Criteri di gruppo, vedi [Console Gestione Criteri di gruppo](https://go.microsoft.com/fwlink/?LinkId=532759).
    
2. Fai clic con il pulsante destro del mouse sul nodo **Oggetti Criteri di gruppo** e seleziona **Nuovo** nel menu.
    
3. Nella finestra di dialogo **Nuovo oggetto Criteri di gruppo** immetti un nome per l'oggetto Criteri di gruppo, ad esempioMakeLyncDefaultUI, quindi fai clic su **OK**.
    
4. Fai clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo creato, quindi seleziona **Modifica** dal menu.
    
5. Nella finestra **Editor Gestione Criteri di gruppo** espandi **Configurazione utente**, espandi **Preferenze**, quindi **Impostazioni di Windows** e seleziona il nodo **Registro di sistema**.
    
6. Fai clic con il pulsante destro del mouse sul nodo **Registro di sistema**, quindi seleziona **Nuovo** > **Elemento Registro di sistema**.
    
7. Nella finestra di dialogo **Nuove proprietà Registro di sistema** aggiorna i seguenti elementi:
    
   |**Campo**|**Valore da selezionare o immettere**|
   |:-----|:-----|
   |**Azione** <br/> |**Create** <br/> |
   |**Hive** <br/> | HKEY_CURRENT_USER <br/> |
   |**Percorso chiave** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nome valore** <br/> |EnableSkypeUI  <br/> |
   |**Tipo valore** <br/> |REG_BINARY  <br/> |
   |**Dati valore** <br/> |00000000  <br/> |
   
8. Fai clic su **OK** per salvare le modifiche e quindi chiudi l'oggetto Criteri di gruppo.
    
Successivamente dovrai collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui vuoi assegnare il criterio, ad esempio un'unità organizzativa.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Per usare l'oggetto Criteri di gruppo per assegnare il criterio

1. In Console Gestione Criteri di gruppo fai clic con il pulsante destro del mouse sull'unità organizzativa a cui vuoi assegnare il criterio e quindi seleziona **Collega a un oggetto Criteri di gruppo esistente**.
    
2. Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo** seleziona l'oggetto Criteri di gruppo creato, quindi seleziona **OK**.
    
3. Nel computer dell'utente di destinazione apri un prompt dei comandi e digita il seguente comando:
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. Al prompt dei comandi digita il seguente comando:
    
    **gpresult /r**
    
    Di seguito dovresti visualizzare "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.
    
Puoi inoltre verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema. Aprire l'editor del registro di sistema e passare alla chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** . Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, visualizzerai un valore denominato EnableSkypeUI con il valore 0.
  

