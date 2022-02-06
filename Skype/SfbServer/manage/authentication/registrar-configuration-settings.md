---
title: Gestire le impostazioni di configurazione della funzione di registrazione in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Riepilogo: gestire le impostazioni di configurazione della funzione di registrazione per Skype for Business Server.'
---

# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione della funzione di registrazione in Skype for Business Server
 
**Riepilogo:** Gestire le impostazioni di configurazione della funzione di registrazione Skype for Business Server.
  
È possibile utilizzare la funzione di registrazione per configurare metodi di autenticazione di server proxy. Il protocollo di autenticazione specificato determina il tipo di richieste dei server del pool per i client. I protocolli disponibili sono i seguenti:
  
- **Kerberos** Si tratta dello schema di autenticazione basato su password più forte disponibile per i client, ma in genere è disponibile solo per i client aziendali perché richiede la connessione client a un Centro distribuzione chiavi (controller di dominio Kerberos). Questa impostazione è appropriata se il server deve eseguire solo l'autenticazione dei client aziendali.
    
- **NTLM** Si tratta dell'autenticazione basata su password disponibile per i client che utilizzano uno schema di hashing challenge-response sulla password. È l'unica forma di autenticazione disponibile per i client senza connettività a un Centro distribuzione chiavi (controller di dominio Kerberos), ad esempio gli utenti remoti. Se un server autentica solo utenti remoti, è consigliabile scegliere NTLM.
    
- **Autenticazione certificato** Questo è il nuovo metodo di autenticazione quando il server deve ottenere certificati dai client Lync Telefono Edition, dai telefoni di area comune, Skype for Business e dall'app Lync Windows Store. Nei client Lync Telefono Edition, dopo che un utente ha eseguito l'accesso ed è stato autenticato correttamente fornendo un PIN (Personal Identification Number), Skype for Business Server quindi esegue il provisioning dell'URI SIP al telefono ed esegue il provisioning di un Skype for Business Server  certificato firmato o un certificato utente che identifica Joe (ex: SN=joe@contoso.com ) al telefono. Questo certificato viene utilizzato per l'autenticazione con la funzione di Registrazione avanzata e i servizi Web.
    
> [!NOTE]
> È consigliabile abilitare sia Kerberos sia NTLM quando un server supporta l'autenticazione per client remoti e aziendali. Il server perimetrale e i server interni comunicano per assicurare che ai client remoti venga offerta solo l'autenticazione NTLM. I server in cui è abilitata solo l'autenticazione Kerberos non sono in grado di autenticare gli utenti remoti. Se il server autentica anche gli utenti aziendali, viene utilizzato Kerberos. 
  
Se si utilizzeranno client dell'app Lync Windows Store, è necessario abilitare l'autenticazione dei certificati.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Per creare nuove impostazioni di configurazione della funzione di registrazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.
    
4. Nella pagina **Funzione di registrazione** fare clic su **Nuovo**
    
5. In **Seleziona un servizio** fare clic sul servizio a cui applicare la funzione di registrazione e quindi su **OK**.
    
6. In **Impostazione funzione di registrazione** selezionare una o più opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
   - **Abilita autenticazione Kerberos** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione Kerberos.
    
   - **Abilita autenticazione NTLM** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione NTLM.
    
   - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
7. Fare clic su **Commit**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modificare le impostazioni di configurazione esistenti della funzione di registrazione

È possibile utilizzare la funzione di registrazione per configurare i protocolli di autenticazione dei server proxy. 
  
> [!NOTE]
> Se un server supporta l'autenticazione sia per client remoti che per client aziendali, è consigliabile abilitare sia Kerberos che NTLM. Il server perimetrale e i server interni sono in comunicazione per garantire che ai client remoti sia fornita solo l'autenticazione NTLM. Se in questi server è abilitato solo Kerberos, non sono in grado di autenticare gli utenti remoti. Se attraverso questi server avviene anche l'autenticazione degli utenti aziendali, viene utilizzato Kerberos. 
  
Per modificare una funzione di registrazione esistente, seguire la procedura seguente. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Per modificare le impostazioni di configurazione della funzione di registrazione esistente

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Funzione di registrazione**.
    
4. Nella pagina **Funzione di registrazione** fare clic su un servizio, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica impostazione funzione di registrazione** selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:
    
   - **Abilita autenticazione Kerberos** perché i server del pool emettano richieste utilizzando l'autenticazione Kerberos.
    
   - **Abilita autenticazione NTLM** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione NTLM.
    
   - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
6. Fare clic su **Commit**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Per eliminare le impostazioni di configurazione della funzione di registrazione

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.
    
4. Nella pagina **Funzione di registrazione** digitare il nome della funzione di registrazione che si desidera eliminare nel campo di ricerca, per intero o in parte.
    
5. Nell'elenco fare clic sulla funzione di registrazione desiderata, fare clic su **Modifica**, quindi su **Elimina**.
    
6. Fare clic su **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri di Impostazioni di registrazione tramite Windows PowerShell cmdlet

È possibile eliminare le impostazioni di configurazione della funzione di registrazione utilizzando Windows PowerShell e il cmdlet **Remove-CsProxyConfiguration**. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota [di PowerShell per Microsoft Lync](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/).
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Per rimuovere un set specifico di impostazioni di sicurezza della funzione di registrazione

- Il comando seguente rimuove le impostazioni di sicurezza della funzione di registrazione applicate al server perimetrale atl-edge-011.litwareinc.com:
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione applicate all'ambito del sito

- Il comando seguente rimuove tutte le impostazioni di sicurezza della funzione di registrazione applicate al servizio di registrazione:
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'autenticazione NTLM

- Il comando seguente elimina tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'utilizzo di NTLM per l'autenticazione client:
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Per informazioni dettagliate, [vedere Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
