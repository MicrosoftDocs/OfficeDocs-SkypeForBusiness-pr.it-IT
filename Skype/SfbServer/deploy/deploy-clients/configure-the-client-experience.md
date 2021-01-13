---
title: Configurare l'esperienza client con Skype for business 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for business."
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805956"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurare l'esperienza client con Skype for business 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'esperienza client per gli utenti di Skype for business 2015.
  
Skype for business 2015 offre una nuova esperienza utente basata sull'esperienza del prodotto consumer Skype. Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone note. Per informazioni dettagliate sulla nuova esperienza client, vedere [esplorare Skype for business](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype for Business Server supporta la nuova esperienza client Skype for business così come l'esperienza client Lync. In qualità di amministratore, è possibile scegliere l'esperienza client preferita per gli utenti. Ad esempio, è possibile distribuire l'esperienza client di Lync fino a quando gli utenti dell'organizzazione non sono completamente formati nella nuova esperienza Skype for business. In alternativa, se non sono stati ancora aggiornati tutti gli utenti a Skype for Business Server, è possibile che tutti gli utenti abbiano la stessa esperienza client finché non vengono aggiornati tutti al nuovo server.
  
> [!IMPORTANT]
> Se l'organizzazione ha implementato sia Skype for Business Server che Lync Server, l'esperienza client predefinita diventerà diversa a seconda delle versioni del server e delle impostazioni dell'interfaccia utente. Quando gli utenti lanciano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'esperienza client di Lync. Dopo alcuni minuti, agli utenti viene richiesto di passare alla modalità Lync. Per ulteriori informazioni, vedere **First Launch client Behavior** più avanti in questo argomento.
  
> [!NOTE]
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016 o versione successiva. Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per verificare che non venga avviata con il numero 16. ad esempio: 16. x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurare l'esperienza client

È possibile specificare l'esperienza client che gli utenti dell'organizzazione vedranno utilizzando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI:
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

dove XdsIdentity si riferisce al criterio globale o a un criterio sito denominato.
  
Il comando seguente consente di selezionare l'esperienza client Skype for business per tutti gli utenti dell'organizzazione a cui è applicato il criterio globale (ricordarsi, il sito o i criteri specifici dell'utente eseguono l'override del criterio globale): 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

Il comando seguente consente di selezionare l'esperienza client di Lync per tutti gli utenti dell'organizzazione coinvolti nei criteri globali:
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

Il comando seguente consente di selezionare l'esperienza client Skype for business per tutti gli utenti all'interno del sito Redmond:
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Se si desidera configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente utilizzando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici utilizzando il cmdlet **Grant-CsClientPolicy** .
  
Ad esempio, il comando seguente consente di creare un nuovo criterio client, SalesClientUI, che seleziona l'esperienza client Skype for business:
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

Il comando seguente assegna il criterio, SalesClientUI, a tutti i membri del reparto vendite:
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Primo avvio di comportamenti client

Per impostazione predefinita, quando gli utenti lanciano Skype for business 2015 per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'esperienza client di Lync impostando il valore del parametro EnableSkypeUI su $False come descritto in precedenza. Dopo alcuni minuti, agli utenti verrà richiesto di passare alla modalità Lync.
  
Se si desidera visualizzare l'interfaccia utente di Lync quando gli utenti avviano il client Skype for business per la prima volta, attenersi alla seguente procedura prima che il client venga avviato per la prima volta dopo essere stato aggiornato:
  
1. Verificare che il valore di  `EnableSkypeUI` sia impostato su $false nel criterio che si sta utilizzando come descritto in precedenza.
    
2. Aggiornare il registro di sistema nel computer dell'utente. Si consiglia di eseguire questa operazione prima che gli utenti avviino il client Skype for business ed è necessario eseguire questa operazione una sola volta. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il registro di sistema in un computer aggiunto a un dominio, vedere la sezione più avanti nell'argomento.
    
    Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** creare un nuovo valore **binario** .
    
    Il **nome del valore** deve essere **EnableSkypeUI** e i **dati del valore** devono essere impostati su **00 00 00 00**.
    
    La chiave dovrebbe essere simile alla seguente:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

L'interfaccia utente di Lync verrà visualizzata quando gli utenti avviano il client Skype for business per la prima volta.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controllare la visualizzazione dell'esercitazione sulla schermata iniziale

Quando gli utenti aprono il client Skype for business, il comportamento predefinito consiste nel visualizzare una schermata di benvenuto che include  *7 suggerimenti rapidi che la maggior parte delle persone richiede*. È possibile disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del registro di sistema nel computer client:
  
Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** creare un nuovo **valore DWORD (32 bit)**. Il **nome del valore** deve essere **IsBasicTutorialSeenByUser** e i **dati del valore** devono essere impostati su **1**.
  
La chiave dovrebbe essere simile alla seguente:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Disattivare l'esercitazione del client

Se non si desidera che gli utenti siano in grado di accedere all'esercitazione, è possibile disattivare l'esercitazione client con il seguente valore del registro di sistema:
  
Nella chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** creare un nuovo **valore DWORD (32 bit)**. Il **nome del valore** deve essere **TutorialFeatureEnabled** e i **dati del valore** devono essere impostati su **0**.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

È possibile riattivare l'esercitazione impostando i **dati di valore** su **1**.
  
## <a name="default-client-behaviors"></a>Comportamenti client predefiniti

Se l'organizzazione ha implementato sia Skype for Business Server che Lync Server, l'esperienza client diventerà diversa a seconda delle versioni del server e dell'impostazione dell'interfaccia utente di Skype. Nella tabella seguente viene illustrata l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:
  

|**Versione server**|**Impostazione di EnableSkypeUI**|**Esperienza client**|
|:-----|:-----|:-----|
|Skype for Business Server |Predefiniti  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Vero  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |Predefiniti  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |Vero  <br/> |Skype for Business  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |False  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (senza patch)  <br/> |Predefiniti  <br/> |L'utente ha chiesto di passare alla modalità Lync (l'utente non può passare a Skype for business in un secondo momento)  <br/> |
   
La tabella successiva Visualizza l'esperienza client quando l'amministratore cambia l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:
  

|**Versione server**|**Impostazione di EnableSkypeUI**|**Client UI = Lync**|**Client UI = Skype for business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |Vero  <br/> |L'utente ha chiesto di passare a Skype for business  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Modalità Lync  <br/> |Utente che ha chiesto di passare alla modalità Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |Vero  <br/> |L'utente ha chiesto di passare a Skype for business  <br/> |Skype for Business  <br/> |
|Lync Server 2010 o Lync Server 2013 (con le patch corrette)  <br/> |False  <br/> |Modalità Lync  <br/> |Utente che ha chiesto di passare alla modalità Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (senza patch)  <br/> |Predefiniti  <br/> |Modalità Lync (non è possibile passare a Skype for business)  <br/> |Modalità Lync (non è possibile passare a Skype for business)  <br/> |
   
Le versioni delle patch necessarie per gestire la configurazione del client Skype for business sono le seguenti:
  
- Lync Server 2010-February 2015 Cumulative Update (4.0.7577.710) per Lync Server 2010. Per informazioni, vedere [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-dicembre 2014 Cumulative Update (5.0.8308.857) per Lync Server 2013. Per informazioni, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Creare un oggetto Criteri di gruppo per modificare il registro di sistema in un computer aggiunto a un dominio

L'aggiornamento del registro di sistema per la visualizzazione dell'esperienza client Lync al primo avvio del client Skype for business 2015 deve essere eseguito una sola volta. Se si utilizza un oggetto Criteri di gruppo per aggiornare il registro di sistema, è necessario definire l'oggetto per creare un nuovo valore anziché aggiornare i dati del valore. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, verrà creato dal GPO e i dati del valore verranno impostati su 0. 
  
Nella procedura seguente viene descritto come modificare il registro di sistema in modo che l'esperienza client di Lync venga visualizzata al primo avvio del client Skype for business 2015. È inoltre possibile utilizzare questa procedura per aggiornare il registro di sistema per disabilitare l'esercitazione introduttiva sulla schermata come descritto in precedenza.
  
### <a name="to-create-the-gpo"></a>Per creare l'oggetto Criteri di gruppo

1. Avviare la **console di gestione di criteri di gruppo**.
    
    Per informazioni su come utilizzare la console Gestione criteri di gruppo, vedere [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).
    
2. Fare clic con il pulsante destro del mouse sul nodo **oggetti Criteri di gruppo** e scegliere **nuovo** dal menu.
    
3. Nella finestra di dialogo **nuovo oggetto Criteri** di gruppo immettere un nome per l'oggetto Criteri di gruppo, ad esempio MakeLyncDefaultUI, e quindi fare clic su **OK**.
    
4. Fare clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo appena creato e quindi scegliere **modifica** dal menu.
    
5. In **Editor gestione criteri di gruppo** espandere **Configurazione utente**, espandere **Preferenze**, espandere **impostazioni di Windows** e quindi selezionare il nodo **del registro di sistema** .
    
6. Fare clic con il pulsante destro del mouse sul nodo **del registro di sistema** e scegliere **nuovo**  >  **elemento del registro di sistema**.
    
7. Nella finestra di dialogo **nuove proprietà del registro di sistema** , aggiornare quanto segue:
    
   |**Campo**|**Valore da selezionare o immettere**|
   |:-----|:-----|
   |**Azione** <br/> |**Creare** <br/> |
   |**Alveare** <br/> | HKEY_CURRENT_USER <br/> |
   |**Percorso chiave** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nome valore** <br/> |EnableSkypeUI  <br/> |
   |**Tipo valore** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. Fare clic su **OK** per salvare le modifiche e quindi chiudere l'oggetto Criteri di gruppo.
    
Successivamente, è necessario collegare l'oggetto Criteri di gruppo creato all'insieme di utenti a cui si desidera assegnare il criterio, ad esempio un'unità organizzativa.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Per utilizzare l'oggetto Criteri di gruppo per assegnare il criterio

1. Nella console Gestione criteri di gruppo fare clic con il pulsante destro del mouse sull'unità organizzativa a cui si desidera assegnare il criterio e quindi scegliere **collegamento a un oggetto Criteri** di sistema esistente.
    
2. Nella finestra di dialogo **Seleziona oggetto Criteri** di gruppo selezionare l'oggetto Criteri di gruppo creato e quindi fare clic su **OK**.
    
3. Nel computer dell'utente di destinazione aprire una finestra del prompt dei comandi e digitare il comando seguente:
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. Al prompt dei comandi, digitare il seguente comando:
    
    **gpresult/r**
    
    Dovrebbe essere visualizzato "oggetti Criteri di gruppo assegnati" con il nome del GPO creato in basso.
    
È inoltre possibile verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il registro di sistema nel computer di un utente esaminando il registro di sistema. Aprire l'editor del registro di sistema e passare alla chiave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** . Se l'oggetto Criteri di gruppo ha aggiornato correttamente il registro di sistema, verrà visualizzato un valore denominato EnableSkypeUI con un valore pari a 0.
  

