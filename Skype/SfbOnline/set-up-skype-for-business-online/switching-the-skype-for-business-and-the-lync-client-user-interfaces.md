---
title: Passaggio tra le interfacce utente del client Skype for Business e del client Lync
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: cde636a0919a1cc4e6c8c852e61040f6bee296eb
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857056"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Passaggio tra le interfacce utente del client Skype for Business e del client Lync

[] Nelle organizzazioni che dispongono di Skype for Business online, puoi utilizzare una sessione remota di PowerShell in Office 365 per abilitare gli utenti Skype for Business a utilizzare l'interfaccia utente del client Skype for Business o quella del client Skype for Business (Lync). L'impostazione predefinita prevede che gli utenti utilizzino l'interfaccia utente del client Skype for Business. Se si preferisce utilizzare l'esperienza con client Lync, è possibile gestire il comportamento dei client avvia primo per visualizzare l'interfaccia utente di Lync seguendo i passaggi descritti più avanti in questo argomento.
  
> [!NOTE]
> L'esperienza client Lync 2013 non è prevista per le versioni client di Skype for Business 2016. Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x. 
  
> [!TIP]
> Se si desidera cambiare facilmente interfaccia utente senza necessità di eseguire procedure manuali, visitare l'[Area download Microsoft](https://go.microsoft.com/fwlink/?LinkId=532431) per trovare un script di PowerShell che renderà più semplice l'operazione.
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>Cambio dell'interfaccia utente di Skype for Business per gli utenti

Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione remota di Windows PowerShell che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688) Per altre informazioni, vedi[Configurazione del computer per la gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=534539).
  
> [!IMPORTANT]
> L'impostazione del criterio  _Global_ per il cambio dell'interfaccia utente non verrà applicata a un utente che ha già un criterio personalizzato applicato. Per consentire il cambio dell'interfaccia utente, sarà necessario eseguire il seguente comando per ciascun utente che ha un criterio personalizzato applicato:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> Il criterio  _ClientPolicyEnableSkypeUI_ sostituirà l'impostazione del criterio personalizzato esistente per l'utente.
  
Per abilitare tutti gli utenti dell'organizzazione a utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Se si imposta correttamente il criterio, verrà visualizzato quanto segue:
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Per abilitare tutti gli utenti dell'organizzazione a utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue: 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Se si imposta correttamente il criterio, verrà visualizzato quanto segue:
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Per consentire a un singolo utente dell'organizzazione di utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

Se si imposta correttamente il criterio, verrà visualizzato quanto segue:
  
![Skype for Business Online - Abilitare l'interfaccia utente](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
Per consentire a un singolo utente dell'organizzazione di utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

Se si imposta correttamente il criterio, verrà visualizzato quanto segue:
  
![Skype for Business Online - Interfaccia utente disabilitata](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
Per consentire a più utenti dell'organizzazione di utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Per consentire a più utenti dell'organizzazione di utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue:
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Per consentire a un gruppo di utenti dell'organizzazione di utilizzare il client Skype for Business, aprire una sessione remota di PowerShell e digitare quanto segue:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Per consentire a un gruppo di utenti dell'organizzazione di utilizzare il client Skype for Business (Lync), aprire una sessione remota di PowerShell e digitare quanto segue:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  Il nome dell'utente è il nome account dell'utente al quale dovrebbe essere assegnato il criterio. Il nome account dell'utente può essere immesso in uno dei formati seguenti:>  Indirizzo SIP dell'utente>  Nome dell'entità utente (UPN) dell'utente>  Dominio\\nome utente dell'utente>  Nome visualizzato Active Directory dell'utente
  
[Uso di Windows PowerShell per gestire Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>Impostazioni del criterio di Skype for Business Online

Questa tabella mostra l'esperienza utente quando il criterio viene applicato per la prima volta agli utenti:
  
|**Impostazione del criterio da parte dell'amministratore**|**Interfaccia utente visualizzata**|
|:-----|:-----|
|Il criterio non è impostato. |L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|All'utente verrà richiesto di passare all'interfaccia utente del client Skype for Business (Lync). Gli utenti possono cambiare interfaccia in un secondo momento.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|L'utente utilizzerà l'interfaccia utente del client Skype for Business. |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|L'utente verrà richiesto di passare a Skype per l'interfaccia utente client Business (Lync). L'amministratore potrà in futuro modificare l'impostazione che consentirà agli utenti di passare all'interfaccia utente del client Skype for Business. |
   
Questa tabella mostra l'esperienza utente quando il criterio viene modificato:
  
|**Impostazione del criterio da parte dell'amministratore**|**Interfaccia utente di Skype for Business (Lync)**|**Interfaccia utente di Skype for Business**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|All'utente verrà richiesto di passare all'interfaccia utente del client Skype for Business.  <br/> |L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|L'utente continua a utilizzare il Skype per l'interfaccia Business (Lync).  <br/> |L'utente verrà richiesto di passare a Skype per l'interfaccia utente client Business (Lync).  <br/> |
|Il criterio non è impostato.  <br/> |Se il criterio non è impostato, gli utenti non visualizzeranno mai Skype per l'interfaccia utente client Business (Lync). Gli utenti utilizzeranno sempre l'interfaccia utente del client Skype for Business.  <br/> |L'utente continuerà a utilizzare l'interfaccia utente del client Skype for Business.  <br/> |
   
Questa tabella visualizza tutti i criteri personalizzati online disponibili. Sono stati creati nuovi criteri per dare agli amministratori la flessibilità di mantenere il vecchio criterio personalizzato durante il passaggio da un flag EnableSkypeUI all'altro. Utilizza i cmdlet indicati in precedenza per concedere agli utenti uno dei seguenti criteri.
  
|**Nome del criterio**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |Falso|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |Falso|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |Falso|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |Falso|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |Falso|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|Falso|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |Falso|

   
Per iniziare a usare Windows PowerShell, vedere questi argomenti:
  
- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>Comportamenti del client al primo avvio

Per impostazione predefinita, quando gli utenti Skype per le aziende di avvio per la prima volta, sempre visualizzeranno Skype all'interfaccia utente di Business, anche se è stata selezionata l'esperienza con client Lync impostando il criterio client per l'esperienza con client Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) come descritto in precedenza. Dopo alcuni minuti, all'utente verrà richiesto di passare alla modalità Lync.
  
Se desideri visualizzare l'interfaccia utente di Lync al primo avvio del client Skype for Business da parte dell'utente, segui questa procedura prima che il client venga avviato per la prima volta in seguito all'aggiornamento:
  
1. Segui i passaggi indicati in precedenza nell'argomento e verifica che il criterio client sia impostato per disabilitare l'interfaccia utente di Skype for Business.
    
2. Aggiorna il Registro di sistema nel computer dell'utente. Esegui l'operazione una sola volta, prima del primo avvio del client Skype for Business da parte dell'utente. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer che fa parte di un dominio, vedi la sezione presente successivamente nell'argomento.
    
    Nella chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** crea un nuovo valore **Binary**.
    
    **Nome valore** deve essere **EnableSkypeUI**, mentre **Dati valore** deve essere impostato su **00 00 00 00**.
    
    La chiave dovrebbe avere un aspetto simile al seguente:
    
    [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab" = DWORD: 00000001
    
    "CanShareOneNoteInCollab" = DWORD: 00000001
    
    "CanAppShareInCollab" = DWORD: 00000001
    
    "EnableSkypeUI" = hex: 00, 00, 00,00
    
L'interfaccia utente di Lync verrà visualizzata al primo avvio del client Skype for Business da parte dell'utente.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controllare la visualizzazione dell'esercitazione nella schermata iniziale

Quando si apre Skype per client di Business, il comportamento predefinito consiste nel visualizzare una schermata di benvenuto contenente *la maggior parte delle persone 7 suggerimenti rapidi chiedono*. Puoi disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:
  
Nella chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** crea un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **IsBasicTutorialSeenByUser**, mentre **Dati valore** deve essere impostato su **1**.
  
La chiave dovrebbe avere un aspetto simile al seguente:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Disattivare l'esercitazione nel client

Se non vuoi che gli utenti siano in grado di accedere all'esercitazione, puoi disattivare l'esercitazione nel client con il seguente valore del Registro di sistema:
  
Nella chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** crea un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **TutorialFeatureEnabled**, mentre **Dati valore** deve essere impostato su **0**.
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Puoi riattivare l'esercitazione impostando **Dati valore** su **1**.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer che fa parte di un dominio

L'aggiornamento del Registro di sistema per la visualizzazione dell'esperienza client Lync al primo avvio del client Skype for Business da parte dell'utente deve essere eseguito una sola volta. Se usi un oggetto Criteri di gruppo per aggiornare il Registro di sistema, devi definire l'oggetto per creare un nuovo valore anziché aggiornare Dati valore. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposterà Dati valore su 0.
  
Nella seguente procedura viene illustrato come modificare il Registro di sistema in modo che l'esperienza client Lync venga visualizzata al primo avvio del client Skype for Business da parte dell'utente. Puoi inoltre utilizzare questa procedura per aggiornare il Registro di sistema e disabilitare l'esercitazione nella schermata iniziale come descritto in precedenza.
  
 **Per creare l'oggetto Criteri di gruppo**
  
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
|**Percorso chiave** <br/> |Software\\Microsoft\\Office\\Lync  <br/> |
|**Nome valore** <br/> |EnableSkypeUI  <br/> |
|**Tipo valore** <br/> |REG_BINARY  <br/> |
|**Dati valore** <br/> |00000000  <br/> |
   
Fai clic su **OK** per salvare le modifiche e quindi chiudi l'oggetto Criteri di gruppo.
    
Successivamente dovrai collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui vuoi assegnare il criterio, ad esempio un'unità organizzativa.
  
 **Utilizzare l'oggetto Criteri di gruppo per assegnare il criterio**
  
1. In Console Gestione Criteri di gruppo fai clic con il pulsante destro del mouse sull'unità organizzativa a cui vuoi assegnare il criterio e quindi seleziona **Collega a un oggetto Criteri di gruppo esistente**.
    
2. Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo** seleziona l'oggetto Criteri di gruppo creato, quindi seleziona **OK**.
    
3. Nel computer dell'utente di destinazione apri un prompt dei comandi e digita il seguente comando:
    
    **gpupdate /target:user**
    
    Durante l'applicazione dell'oggetto Criteri di gruppo verrà visualizzato il messaggio "Aggiornamento criteri in corso...". Al termine dell'operazione verrà visualizzato il messaggio "Aggiornamento dei criteri utente completato".
    
4. Al prompt dei comandi digita il seguente comando:
    
    **gpresult /r**
    
    Di seguito dovresti visualizzare "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.
    
Puoi inoltre verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema. Apri Editor del Registro di sistema e accedi alla chiave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, visualizzerai un valore denominato EnableSkypeUI con il valore 0.
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 