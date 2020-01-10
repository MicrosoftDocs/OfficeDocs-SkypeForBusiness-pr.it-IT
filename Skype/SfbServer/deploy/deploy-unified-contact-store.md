---
title: "Distribuire l'archivio contatti unificato in Skype for Business Server "
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: "Riepilogo: abilitare l'archivio contatti unificato in Skype for Business Server."
ms.openlocfilehash: 6cadba38f40a8ff12501e0fe73f4243dc96a5831
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003066"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Distribuire l'archivio contatti unificato in Skype for Business Server
 
**Riepilogo:** Abilitare l'archivio contatti unificato in Skype for Business Server.
  
L'abilitazione dell'archivio contatti unificato in Skype for Business Server non richiede le impostazioni della topologia. Per abilitare l'archivio contatti unificato per gli utenti:
  
- Il criterio archivio contatti unificato è abilitato (il valore predefinito è abilitato).
    
- Gli utenti accedono con Skype for business almeno una volta.
    
Dopo la migrazione dei contatti di un utente, che avviene automaticamente quando un utente accede con Skype for business, l'utente può accedere e gestire i contatti di Skype for business da Skype for business, Outlook 2013 o Outlook Web Access. Non è necessario che l'utente abbia effettuato l'accesso a Skype for business per gestire i propri contatti da Outlook o Outlook Web Access.
  
> [!IMPORTANT]
> Se un utente accede da Skype for business dopo la migrazione, i contatti e i gruppi sono disponibili e aggiornati, ma l'utente non può gestire (ovvero aggiungere, eliminare, trasferire, contrassegnare, UNTAG o modificare) i contatti. 
  
## <a name="enable-users-for-unified-contact-store"></a>Abilitare gli utenti per l'archivio contatti unificato

Quando si distribuisce Skype for Business Server e si pubblica la topologia, per impostazione predefinita l'archivio contatti unificato è abilitato per tutti gli utenti. Non è necessario eseguire altre azioni per abilitare l'archiviazione di contatti unificati dopo la distribuzione di Skype for Business Server. Tuttavia, puoi usare il cmdlet **Set-CsUserServicesPolicy** per personalizzare gli utenti che dispongono di un archivio contatti unificato disponibile. Puoi abilitare questa funzionalità a livello globale, per sito, per tenant o per singoli o gruppi di persone.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Per abilitare gli utenti per l'archivio contatti unificato

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire una delle operazioni seguenti:
    
   - Per abilitare l'archivio contatti unificato a livello globale per tutti gli utenti di Skype for Business Server, tra i seguenti cmdlet dell'interfaccia della riga di comando di Windows PowerShell:
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Per abilitare l'archivio contatti unificato per gli utenti di un sito specifico, al prompt digitare:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Ad esempio:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Per abilitare l'archivio contatti unificato dal tenant, al prompt digitare:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Ad esempio:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Per abilitare l'archivio contatti unificato per utenti specifici, al prompt digitare:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > È anche possibile usare l'alias utente o l'URI SIP anziché il nome visualizzato dell'utente. 
  
    Ad esempio:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > Nell'esempio precedente il primo comando crea un nuovo criterio per utente denominato UCS abilitato agli utenti con il flag UcsAllowed impostato su true. Il secondo comando assegna i criteri all'utente con il nome visualizzato Ken di riferimento, il che significa che Ken è ora abilitato per l'archivio contatti unificato.
  
## <a name="migrate-users-to-unified-contact-store"></a>Eseguire la migrazione degli utenti nell'archivio contatti unificato

I contatti di un utente vengono automaticamente migrati nel server di Exchange 2013 quando l'utente:
  
- È stato assegnato un criterio servizi utente con UcsAllowed impostato su true.
    
- È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha eseguito l'accesso alla cassetta postale almeno una volta.
    
- Accede usando un client Rich di Skype for business.
    
Se l'utente esegue l'accesso con un client Lync o una versione precedente o se l'utente non è connesso a un server di Exchange 2013, il criterio servizi utente viene ignorato e i contatti dell'utente rimangono in Skype for Business Server.
  
Puoi determinare se i contatti di un utente sono stati migrati usando uno dei metodi seguenti: 
  
- Selezionare la chiave del registro di sistema seguente nel computer client:
    
    HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<URL\>SIP \UCS
    
    Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene un valore di InUCSMode con il valore 2165.
    
- Eseguire il cmdlet **Test-CsUnifiedContactStore** . Nella riga di comando di Skype for Business Server Management Shell digitare:
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati in archivio contatti unificato.
    
## <a name="roll-back-migrated-users"></a>Eseguire il rollback degli utenti migrati

Se è necessario eseguire il rollback della funzionalità archivio contatti unificato, ripristinare i contatti solo se l'utente viene spostato di nuovo in Exchange 2010 o Lync Server 2010. Per eseguire il rollback, disabilitare il criterio per l'utente e quindi il cmdlet **Invoke-CsUcsRollback** . Solo l'uso di **Invoke-CsUcsRollback** da solo non è sufficiente per garantire un rollback permanente, perché la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non è disabilitato. Se ad esempio viene eseguito il rollback di un utente perché Exchange 2013 viene eseguito il rollback in Exchange 2010 e la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato è ancora abilitato per l'utente nei criteri servizi utente.
  
Il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Skype for Business Server nelle situazioni seguenti:
  
- Quando gli utenti vengono spostati da Skype for Business Server a Microsoft Lync Server 2013 o Lync Server 2010. 
    
- Quando gli utenti vengono migrati, ad esempio quando un utente viene spostato da Skype for business online a Skype for Business Server locale o viceversa.
    
L'importazione di dati dell'archivio contatti unificati da un database di backup può causare il danneggiamento dei dati dell'archivio contatti unificati se la modalità archivio contatti unificata è cambiata tra l'esportazione e l'importazione. Ad esempio:
  
- Se si esportano elenchi di contatti prima che i contatti degli utenti vengano migrati a Exchange 2013 e quindi, dopo la migrazione, importino gli stessi dati, i dati dell'archivio contatti unificato e gli elenchi di contatti saranno danneggiati.
    
- Se si esportano dati utente dopo la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, i dati vengono importati dopo la migrazione, i dati dell'archivio contatti unificati e gli elenchi di contatti saranno danneggiati.
    
> [!IMPORTANT]
> Prima di trasferire una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve verificare che l'amministratore di Skype for Business Server abbia prima eseguito il rollback dei contatti degli utenti di Skype for Business Server da Exchange 2013 a Skype for Business Server. Per ripristinare i contatti degli archivi di contatti unificati in Skype for Business Server, vedere procedura "per ripristinare i contatti dell'archivio contatti unificati da Exchange 2013 a Skype for Business Server" più avanti in questa sezione. 
  
 **Come ripristinare i contatti utente:** Se si usa il cmdlet **Move-CsUser** per spostare gli utenti tra Skype for business server 2015 e lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti unificato quando sposta gli utenti da skype for Business Server 2015 a Lync Server 2010. **Move-CsUser** non Disabilita i criteri dell'archivio contatti unificato, quindi la migrazione all'archivio contatti unificato si ripresenta se l'utente viene spostato di nuovo in Skype for Business Server 2015.
  

