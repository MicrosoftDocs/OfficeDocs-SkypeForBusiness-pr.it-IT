---
title: "Distribuire l'archivio contatti unificato in Skype for Business Server "
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
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: "Riepilogo: abilitare l'archivio contatti unificato in Skype for Business Server."
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812556"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Distribuire l'archivio contatti unificato in Skype for Business Server
 
**Riepilogo:** Abilitare l'archivio contatti unificato in Skype for Business Server.
  
L'abilitazione dell'archivio contatti unificato in Skype for Business Server non richiede alcuna impostazione della topologia. Per abilitare l'archivio contatti unificato per gli utenti:
  
- I criteri dell'archivio contatto unificati sono abilitati (abilitati per impostazione predefinita).
    
- Gli utenti a log in con Skype for Business almeno una volta.
    
Dopo la migrazione dei contatti di un utente, che avviene automaticamente quando un utente accede con Skype for Business, l'utente può accedere e gestire i propri contatti Skype for Business da Skype for Business, Outlook 2013 o Outlook Web Access. L'utente non deve essere connesso a Skype for Business per gestire i propri contatti da Outlook o Outlook Web Access.
  
> [!IMPORTANT]
> Se un utente accede da Skype for Business dopo la migrazione, i contatti e i gruppi sono disponibili e aggiornati, ma l'utente non può gestire (ovvero aggiungere, eliminare, spostare, contrassegnare, rimuovere tag o modificare) tali contatti. 
  
## <a name="enable-users-for-unified-contact-store"></a>Abilitare gli utenti per l'archivio contatti unificato

Quando si distribuisce Skype for Business Server e si pubblica la topologia, l'archivio contatti unificato è abilitato per tutti gli utenti per impostazione predefinita. Non è necessario eseguire ulteriori azioni per abilitare l'archivio contatti unificato dopo aver distribuito Skype for Business Server. Tuttavia, è possibile utilizzare il cmdlet **Set-CsUserServicesPolicy** per decidere a quali utenti rendere l'archivio unificato per i contatti disponibile. È possibile abilitare questa caratteristica a livello globale, di sito, tenant, o per utenti singoli o gruppi di utenti.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Per abilitare gli utenti all'archivio unificato contatti

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business** e quindi Skype for Business Server Management **Shell.**
    
2. Eseguire una delle operazioni seguenti:
    
   - Per abilitare l'archivio contatti unificato a livello globale per tutti gli utenti di Skype for Business Server, eseguire il cmdlet seguente nell'interfaccia della riga di comando di Windows PowerShell seguente:
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Per abilitare l'archivio contatti unificato per gli utenti di un sito specifico, digitare quanto segue:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Ad esempio:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Per abilitare l'archivio contatti unificato in base al tenant, al prompt dei comandi digitare:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Ad esempio:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Per abilitare l'archivio contatti unificato per utenti specifici, al prompt dei comandi digitare:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Al posto del nome visualizzato dell'utente, è inoltre possibile utilizzare alias utente o URI SIP. 
  
    Ad esempio:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > Nell'esempio precedente, il primo comando crea un nuovo criterio per utente chiamato UCS Enabled Users, con il contrassegno UcsAllowed impostato su True. Il secondo comando assegna il criterio all'utente con nome visualizzato Ken Myer, e pertanto Ken Myer è ora abilitato all'archivio unificato per i contatti.
  
## <a name="migrate-users-to-unified-contact-store"></a>Eseguire la migrazione degli utenti all'archivio contatti unificato

I contatti di un utente vengono migrati automaticamente al server Exchange 2013 quando l'utente:
  
- All'utente sono stati assegnati servizi utente per cui UcsAllowed è impostato su True.
    
- È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha effettuato l'accesso alla cassetta postale almeno una volta.
    
- L'utente effettua l'accesso utilizzando un rich-client Skype for Business.
    
Se l'utente esegue l'accesso con un client Lync o precedente o se l'utente non è connesso a un server Exchange 2013, i criteri servizi utente vengono ignorati e i contatti dell'utente rimangono in Skype for Business Server.
  
È possibile stabilire se i contatti di un utente sono stati migrati usando uno dei metodi seguenti: 
  
- Verificare la chiave del Registro di sistema seguente nel computer client:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ SIP URL \> \UCS
    
    Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene il valore InUCSMode con un valore pari a 2165.
    
- Eseguire il cmdlet **Test-CsUnifiedContactStore**. Nella riga di comando di Skype for Business Server Management Shell digitare:
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati nell'archivio contatti unificato.
    
## <a name="roll-back-migrated-users"></a>Eseguire il rollback degli utenti migrati

Se è necessario eseguire il rollback della funzionalità archivio contatti unificato, ripristinare i contatti solo se si sposta l'utente in Exchange 2010 o Lync Server 2010. Per eseguire il rollback, disabilitare il criterio per l'utente e quindi eseguire il cmdlet **Invoke-CsUcsRollback**. La sola esecuzione di **Invoke-CsUcsRollback** non è sufficiente ad assicurare un rollback permanente, in quanto la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non viene disabilitato. Ad esempio, se viene eseguito il rollback di un utente perché exchange 2013 viene riportato a Exchange 2010 e quindi la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato sia ancora abilitato per l'utente nei criteri dei servizi utente.
  
Il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Skype for Business Server nelle situazioni seguenti:
  
- Quando gli utenti vengono spostati da Skype for Business Server a Microsoft Lync Server 2013 o Lync Server 2010. 
    
- Quando gli utenti vengono migrati in locale, ad esempio quando un utente viene spostato da Skype for Business online a Skype for Business Server in locale o viceversa.
    
L'importazione dei dati dell'archivio contatti unificato da un database di backup può danneggiare i dati dell'archivio e degli utenti se la modalità dell'archivio stesso è cambiata tra l'esportazione e l'importazione. Ad esempio:
  
- Se si esportano gli elenchi contatti prima della migrazione dei contatti degli utenti a Exchange 2013 e quindi, dopo la migrazione, importare gli stessi dati, i dati dell'archivio contatti unificato e gli elenchi contatti saranno danneggiati.
    
- Se si esportano i dati degli utenti dopo aver eseguito la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, importare i dati dopo la migrazione, i dati dell'archivio contatti unificato e gli elenchi contatti saranno danneggiati.
    
> [!IMPORTANT]
> Prima di spostare una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve assicurarsi che l'amministratore di Skype for Business Server abbia prima eseguito il rollback dei contatti utente di Skype for Business Server da Exchange 2013 a Skype for Business Server. Per ripristinare i contatti dell'archivio contatti unificato in Skype for Business Server, vedere la procedura "Per ripristinare i contatti dell'archivio contatti unificato da Exchange 2013 a Skype for Business Server" più avanti in questa sezione. 
  
 **Come eseguire il rollback dei contatti utente:** Se si utilizza il cmdlet **Move-CsUser** per spostare gli utenti tra Skype for Business Server 2015 e Lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti unificato quando sposta gli utenti da Skype for Business Server 2015 a Lync Server 2010. **Move-CsUser** non disabilita i criteri dell'archivio contatti unificato, quindi la migrazione all'archivio contatti unificato si ripeterà se l'utente viene spostato di nuovo in Skype for Business Server 2015.
  

