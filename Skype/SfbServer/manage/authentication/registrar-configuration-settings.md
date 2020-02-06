---
title: Gestire le impostazioni di configurazione del registrar in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Riepilogo: gestire le impostazioni di configurazione del registrar per Skype for Business Server.'
ms.openlocfilehash: 0c4529fb7343cf3db1e516858987a3ba60435513
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818758"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione del registrar in Skype for Business Server
 
**Riepilogo:** Gestire le impostazioni di configurazione del registrar per Skype for Business Server.
  
È possibile usare il registrar per configurare i metodi di autenticazione del server proxy. Il protocollo di autenticazione specificato determina il tipo di problemi che i server del pool rilasciano ai client. I protocolli disponibili sono:
  
- **Kerberos** Questo è lo schema di autenticazione basato su password più forte disponibile per i client, ma in genere è disponibile solo per i client aziendali, perché richiede la connessione del client a un centro distribuzione chiave (controller di dominio Kerberos). Questa impostazione è appropriata se il server autentica solo i client aziendali.
    
- **NTLM** Questa è l'autenticazione basata su password disponibile per i client che usano uno schema di hash per la risposta alla richiesta di verifica sulla password. Questa è l'unica forma di autenticazione disponibile per i client senza connettività a un centro distribuzione chiave (controller di dominio Kerberos), ad esempio utenti remoti. Se un server esegue l'autenticazione solo per gli utenti remoti, è necessario scegliere NTLM.
    
- **Autenticazione del certificato** Questo è il nuovo metodo di autenticazione quando il server deve ottenere i certificati da client Lync Phone Edition, telefoni area comune, Skype for business e l'app Lync di Windows Store. Nei client di Lync Phone Edition, dopo che un utente ha effettuato l'accesso ed è stato autenticato fornendo un PIN (Personal Identification Number), Skype for Business Server applica quindi l'URI SIP al telefono e prevede un certificato firmato Skype for Business Server o un certificato utente che identifica Joe (es: SN=joe@contoso.com) al telefono. Questo certificato viene usato per l'autenticazione con il registrar e i servizi Web.
    
> [!NOTE]
> È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali. Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti. Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti. Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos. 
  
Se si utilizzeranno i client delle app Lync di Windows Store, è necessario abilitare l'autenticazione dei certificati.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Per creare nuove impostazioni di configurazione del registrar

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.
    
4. Nella pagina **registrar** fare clic su **nuovo**
    
5. In **Seleziona un servizio**fare clic sul servizio a cui deve essere applicato il registrar e quindi fare clic su **OK**.
    
6. In **nuova impostazione registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
   - **Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.
    
   - **Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.
    
   - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.
    
7. Fare clic su **Commit**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modificare le impostazioni di configurazione del registrar esistenti

È possibile usare il registrar per configurare i protocolli di autenticazione del server proxy. 
  
> [!NOTE]
> È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali. Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti. Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti. Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos. 
  
Seguire questa procedura per modificare un registrar esistente. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Per modificare le impostazioni di configurazione del registrar esistenti

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.
    
4. Nella pagina **registrar** fare clic su un servizio, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
   - **Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.
    
   - **Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.
    
   - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.
    
6. Fare clic su **Commit**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Per eliminare le impostazioni di configurazione del registrar

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.
    
4. Nella pagina **registrar** e nel campo di ricerca digitare tutto o parte del nome del registrar che si vuole eliminare.
    
5. Nell'elenco fare clic sul registrar desiderato, fare clic su **modifica**e quindi su **Elimina**.
    
6. Fare clic su **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione del registrar tramite i cmdlet di Windows PowerShell

Per eliminare le impostazioni di configurazione del registrar, è possibile usare Windows PowerShell e il cmdlet **Remove-CsProxyConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Per rimuovere un set specifico di impostazioni di sicurezza del registrar

- Il comando seguente rimuove le impostazioni di sicurezza del registrar applicate alla atl-edge-011.litwareinc.com di Edge Server:
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di sicurezza del registrar applicate all'ambito del sito

- Il comando seguente rimuove tutte le impostazioni di sicurezza del registrar applicate al servizio Registrar:
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Per rimuovere tutte le impostazioni di sicurezza del registrar che consentono l'autenticazione NTLM

- Il comando seguente elimina tutte le impostazioni di sicurezza del registrar che consentono l'uso di NTLM per l'autenticazione client:
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Per informazioni dettagliate, vedere [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

